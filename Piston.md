## Piston ##

**From the project documentation:** https://bitbucket.org/jespern/django-piston/wiki/Home

# A mini-framework for Django for creating RESTful APIs. #

Piston is a relatively small Django application that lets you
create application programming interfaces (API) for your sites.

It has several unique features:

  * Ties into Django's internal mechanisms.
  * Supports OAuth out of the box (as well as Basic/Digest or custom auth.)
  * Doesn't require tying to models, allowing arbitrary resources.
  * Speaks JSON, YAML, Python Pickle & XML (and HATEOAS.)
  * Ships with a convenient reusable library in Python
  * Respects and encourages proper use of HTTP (status codes, ...)
  * Has built in (optional) form validation (via Django), throttling, etc.
  * Supports streaming, with a small memory footprint.
  * Stays out of your way.

**NB**: OAuth ships with piston for now, but you are not required to use it. It simply provides some boilerplate in case you want to use it later (consumer/token models, urls, etc.)

# Fully Functional Example #

`urls.py`:

```
from django.conf.urls.defaults import *
from piston.resource import Resource
from piston.authentication import HttpBasicAuthentication

from myapp.handlers import BlogPostHandler, ArbitraryDataHandler

auth = HttpBasicAuthentication(realm="My Realm")
ad = { 'authentication': auth }

blogpost_resource = Resource(handler=BlogPostHandler, **ad)
arbitrary_resource = Resource(handler=ArbitraryDataHandler, **ad)

urlpatterns += patterns('',
    url(r'^posts/(?P<post_slug>[^/]+)/$', blogpost_resource), 
    url(r'^other/(?P<username>[^/]+)/(?P<data>.+)/$', arbitrary_resource), 
)
```

`handlers.py`:

```
import re

from piston.handler import BaseHandler
from piston.utils import rc, throttle

from myapp.models import Blogpost

class BlogPostHandler(BaseHandler):
    allowed_methods = ('GET', 'PUT', 'DELETE')
    fields = ('title', 'content', ('author', ('username', 'first_name')), 'content_size')
    exclude = ('id', re.compile(r'^private_'))
    model = Blogpost

    @classmethod
    def content_size(self, blogpost):
        return len(blogpost.content)

    def read(self, request, post_slug):
        post = Blogpost.objects.get(slug=post_slug)
        return post

    @throttle(5, 10*60) # allow 5 times in 10 minutes
    def update(self, request, post_slug):
        post = Blogpost.objects.get(slug=post_slug)

        post.title = request.PUT.get('title')
        post.save()

        return post

    def delete(self, request, post_slug):
        post = Blogpost.objects.get(slug=post_slug)

        if not request.user == post.author:
            return rc.FORBIDDEN # returns HTTP 401

        post.delete()

        return rc.DELETED # returns HTTP 204

class ArbitraryDataHandler(BaseHandler):
    methods_allowed = ('GET',)

    def read(self, request, username, data):
        user = User.objects.get(username=username)

        return { 'user': user, 'data_length': len(data) }
```