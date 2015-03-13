# Introduction #
This article is a stub.


# Restish #
_From [An Introduction to Restish](http://ish.io/embedded/restish/introduction.html)_

Restish is a simple to use, lightweight WSGI web framework and library with a strong focus on resources, request/response, URLs and content negotiation. Restish has very few dependencies and does not assume any particular templating or database engine.

A key feature of Restish is that it makes no use of thread-locals or any other concurrency-dependent contexts and so works equally well under Paste Deploy or a thread-less web server such as Spawning.

# Code Sample #
_From [Restish Resources](http://ish.io/embedded/restish/resources.html)_

```
import logging
from restish import http, resource

log = logging.getLogger(__name__)

class Root(resource.Resource):

    @resource.GET()
    def html(self, request):
        return http.ok([('Content-Type', 'text/html')],
            "<p>Hello from myproject!</p>")
```