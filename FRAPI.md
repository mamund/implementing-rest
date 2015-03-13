# FRAPI, a RESTful API Framework #
http://getfrapi.com

FRAPI is a new type of framework that embraces the standards and mindset of how the web is modeled. Instead of being a general purpose framework like the Zend Framework, Symfony, Cake, Lithium, etc. which are great for building web applications, FRAPI aims at removing the whole frontend layer complexity that handling REST calls can bring.

FRAPI is a RESTful API Framework that allows developers to rapidly develop RESTful APIs that are easily scalable and highly performant. FRAPI consists of two specific parts: The administration interface and the public API.

## Administrative Interface ##
The FRAPI administration interface is the section of the FRAPI framework where API developers go to easily manage their APIs. The administration interface allows developers to easily create API calls — resources, actions, URIs — it allows developer to manage API errors, output formats and also test their APIs. Another very interesting aspect of the FRAPI administration interface is the ability to generate third party API documentation.

When creating API calls — resources, actions, URIs, etc — the administration interface will also generate PHP code that is used by the developers to handle the different REST calls. The only thing left to do for developers is to write their business logic and datasource connectors and plug them in the generated FRAPI REST handlers — executeGet(), executePost(), executePut(), executeDelete(), executeHead()

Because of its nature, the administration interface asks the developers who are managing their API to enter a description when creating a new action and when creating a new error. From within the administration interface, an API owner can generate significantly relevant documentation that can be then passed down as an API reference to third party developers — The generated documentation can be exported to HTML, Text, Markdown or PDF.

## High performance developer facing API ##
When a developer is done creating and generating actions using the administration interface, the web-service (API) becomes available to third party companies and third party developers. By opening your data and distributing it to other marketing channels, you can easily broaden your market and gain more customers, adopters and users of your service/product.

## At heart ##
The essence of the FRAPI public API lies in it's simplicity. Whilst the administration interface can get complex, the public API really only creates a bridge between your data and third party developers without having you worrying about how the data has to be formatted or even if you are correctly handling the requests from your customers. The public API takes care of handling the calls and returning the desired results to your API consumers.

## Examples ##


```
#curl -v http://api/frapi/testing/1 -H 'Accept: application/json'
about to connect() to api.frapi port 80 (#0)
*   Trying 127.0.0.1... connected
* Connected to api.frapi (127.0.0.1) port 80 (#0)
> GET /testing/1 HTTP/1.1
> User-Agent: curl/7.17.1 (i386-apple-darwin9.3.0) libcurl/7.17.1 OpenSSL/0.9.7l zlib/1.2.3 libssh2/0.18
> Host: api.frapi
> Accept: application/json
> 
< HTTP/1.1 200 OK
< Date: Mon, 17 Jan 2011 20:36:00 GMT
< Server: Apache/2.0.63 (Unix) mod_ssl/2.0.63 OpenSSL/0.9.7l DAV/2 PHP/5.3.1-dev
< X-Powered-By: PHP/5.3.1-dev
< Access-Control-Allow-Origin: *
< Content-Length: 75
< Content-Type: application/json; charset=utf-8
< 
* Connection #0 to host api.frapi left intact
* Closing connection #0
{"success":true}
```

FRAPI handles content negotiation with xml, json, printr, php, html, custom jsonp, custom xml, etc. It is trivial for developers to add new
output handlers and easier for developers of APIs to feed their data through to the consumers.

Another interesting point is that FRAPI comes with builtin JSONP that requires only minimal considering by the developers of said APIs.

## Developers Handbook ##
The FRAPI team likes to work on a little [Developers handbook](http://frapi.github.com/). If you would like more information, you are welcome
to join us on irc.freenode.org and talk on #frapi

## Links ##

Code: http://github.com/frapi/frapi
Site: http://getfrapi.com
IRC:  [irc://frapi@irc.freenode.org](irc://frapi@irc.freenode.org)
Mailing list and groups: See the site for developers mailing list and user's general mailing list.