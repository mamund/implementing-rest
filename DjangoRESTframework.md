# Introduction #

Django REST framework is a lightweight REST framework for Django, that aims to make it easy to build well-connected, self-describing RESTful Web APIs.

**Browse example APIs created with Django REST framework:** http://api.django-rest-framework.org/

Features:

  * Automatically provides a Django admin style browse-able self-documenting API. http://api.django-rest-framework.org
  * Clean, simple, views for Resources, using Django's new class based views.
  * Support for ModelResources with out-of-the-box default implementations and input validation.
  * Pluggable emitters, parsers, validators and authenticators - Easy to customise.
  * Content type negotiation using HTTP Accept headers.
  * Optional support for forms as input validation.
  * Modular architecture - MixIn classes can be used without requiring the Resource or ModelResource classes.

The django-rest-framework project is hosted as a mercurial repository on bitbucket https://bitbucket.org/tomchristie/django-rest-framework and is available on PyPI. http://pypi.python.org/pypi/djangorestframework

For questions, thoughts and feedback please head on over to the discussion group. http://groups.google.com/group/django-rest-framework

Bug reports are greatful received on the issue tracker. https://bitbucket.org/tomchristie/django-rest-framework/issues?sort=version

If you're feeling particularly enthusiastic there's even a blog. http://blog.django-rest-framework.org

# Requirements #

  * Python (2.5, 2.6, 2.7 supported)
  * Django (1.2, 1.3 supported)


# Installation & Setup #


You can install Django REST framework using `pip` or `easy_install`:

```
    pip install djangorestframework
```

Or download the current release from BitBucket:

  * https://bitbucket.org/tomchristie/django-rest-framework/downloads/django-rest-framework-0.1.tar.gz
  * https://bitbucket.org/tomchristie/django-rest-framework/downloads/django-rest-framework-0.1.zip

Or get the latest development version using mercurial::

```
    hg clone https://bitbucket.org/tomchristie/django-rest-framework
```

To install Django REST framework to your `site-packages` directory, run the `setup.py` script:

```
    python setup.py install
```

To add django-rest-framework to a Django project:

  * Ensure that the `djangorestframework` directory is on your `PYTHONPATH`.
  * Add `djangorestframework` to your `INSTALLED_APPS`.

# Getting Started #

Using Django REST framework can be as simple as adding a few lines to your urlconf and adding a permalink to your model.

`urls.py`:

```
    from django.conf.urls.defaults import patterns, url
    from djangorestframework import ModelResource, RootModelResource
    from models import MyModel

    urlpatterns = patterns('',
        url(r'^$', RootModelResource.as_view(model=MyModel)),
        url(r'^(?P<pk>[^/]+)/$', ModelResource.as_view(model=MyModel), name='my-model'),
     )
```

`models.py`:

```
    class MyModel(models.Model):

        # (Rest of model definition...)

        @models.permalink
        def get_absolute_url(self):
            return ('my-model', (self.pk,))
```

**For more information see the official documentation:** http://django-rest-framework.org