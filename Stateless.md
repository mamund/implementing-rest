# Introduction #

Even though the web builds on the stateless HTTP protocol, it is easy to build systems which are not stateless, and thus miss out on some important benefits of the REST architectural style.

[Wikipedia defines](http://en.wikipedia.org/wiki/Stateless_protocol) a _Stateless (computing) Protocol_ as "_a communications protocol that treats each request as an independent transaction that is unrelated to any previous request so that the communication consists of independent pairs of requests and responses._"  Furthermore, it states "_A stateless protocol does not require the server to retain session information or status about each communications partner for the duration of multiple requests. In contrast, a protocol which requires the keeping of internal state is known as a stateful protocol._" It goes on to cite HTTP as an example of a stateless protocol.  In his disseration, Fielding states that statelessness requires "_each request from client to server must contain all of the information necessary to understand the request, and cannot take advantage of any stored context on the server. Session state is therefore kept entirely on the client._"

# Stateful interactions #

In essence, it means that the server should process each request "independently", and not retain any information or status about the clients making the requests.  For example, a server being asked to `GET /foo` should respond to the request if the client has previously asked to `GET /foo` or even `GET /bar`.  The server does not know "what page" the client is currently looking at; the server doesn't know the various clients' _application state_.

# Benefits #

Fielding asserts that the "_constraint induces the properties of visibility, reliability, and scalability._"  If you violate the stateless constraint it means you might

  * not be able to "understand" a request just by looking at it
  * not be able to recover from partial failuress
  * not be able to scale as well





# Contentious examples #

  * um, shopping cart.  POST an item to /cart/2/additem →  later POST /cart/2/checkout

# "Talk page" :-) #

  * Is there a reason why statelessness and unsafe methods don't fare well together?  Do the benefits of statelessness somehow correlate with safe methods?  Investigate.