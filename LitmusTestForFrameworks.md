## REST Litmus Test for Web Frameworks ##

  * Does the framework respect that an HTTP message does not only consist of a URI? I.e., is dispatch done at least based on the HTTP verb, the URI, the Content-type and Accept headers?
  * Can I easily use the same business logic while returning different content types in the response?
  * Is there support for checking for conditional requests?
  * Are ETags calculated automatically if none are set by the backend logic?
  * Can I (as a framework user) easily read all HTTP request headers?
  * Can I easily set all HTTP response headers?
  * Can I use custom HTTP verbs?
  * Is it obvious and easy how to return correct status codes with responses, and does the framework use them correctly (if it does so at all)?

Along the same lines, here are some questions where a "Yes" indicates that a framework doesn't do things the way they're supposed to be done:

  * Are GET, POST and other requests to the same URI dispatched to the same business logic by default?
  * Am I required to use "extensions" (e.g. ".xml", ".json") to get different representations of the same resource? (Supporting this optionally is OK.)
  * Are there method names in the URI?

Finally, I (Stefan) wonder whether there's any justification for a web framework to support "REST services" as an addition instead of the default, but I'm reluctant to put this into the second list.

_[Stefan Tilkov, July 2010](http://www.innoq.com/blog/st/2010/07/rest_litmus_test_for_web_frame.html)_