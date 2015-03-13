# Introduction #

[Apache CXF](http://cxf.apache.org/) is well known as a services framework for supporting RPC style communication via SOAP.  CXF is also known for its ability to provide REST services through a [JAX-WS Provider/Dispatch|](http://cxf.apache.org/docs/rest-with-jax-ws-provider-and-dispatch.html) which provides an easy mechanism to allow SOAP web service to act more like a REST web service, though it is still essentially RPC/HTTP style approach.

However, CXF does have full blown REST support through JAX-RS and also provides many other features.

http://cxf.apache.org/docs/jax-rs.html

CXF REST has a good spring integration as well as good Maven support.  It is extremely easy to configure.  It does not, however, have any built-in support for [HATEOAS](http://en.wikipedia.org/wiki/HATEOAS).


# Details #

The default JSON encoder in CXF is [Jettison](http://jettison.codehaus.org/), which uses produces JSON via XML using the [Badgerfish Convention](http://badgerfish.ning.com/).  This produces a kind of verbose JSON that is reportedly more difficult to parse using various popular Javascript libraries.

However, CXF supports pluggable JSON encoders and one can easily substitute [Jackson](http://jackson.codehaus.org/) for increased interoperability (and reportedly better performance).