# Introduction #
RESTEasy is a JBoss project that provides various frameworks to help you build RESTful Web Services and RESTful Java applications. It is a fully certified and portable implementation of the JAX-RS specification.

_From the [RESTEasy project home page](http://www.jboss.org/resteasy.html):
## Features ##
The current version of **RESTEasy** has the following features:
  * Fully certified JAX-RS implementation
  * Portable to any app-server/Tomcat that runs on JDK 5 or higher
  * Embeddedable server implementation for junit testing
  * Client framework that leverages JAX-RS annotations so that you can write HTTP clients easily (JAX-RS only defines server bindings)
  * Client "Browser" cache. Supports HTTP 1.1 caching semantics including cache revalidation
  * Server in-memory cache. Local response cache. Automatically handles ETag generation and cache revalidation
  * Rich set of providers for: XML, JSON, YAML, Fastinfoset, Multipart, XOP, Atom, etc.
  * JAXB marshalling into XML, JSON, Jackson, Fastinfoset, and Atom as well as wrappers for maps, arrays, lists, and sets of JAXB Objects.
  * GZIP content-encoding. Automatic GZIP compression/decompression suppport in client and server frameworks
  * Asynchronous HTTP (Comet) abstractions for JBoss Web, Tomcat 6, and Servlet 3.0
  * Asynchronous Job Service.
  * Rich interceptor model.
  * EJB, Seam, Guice, Spring, and Spring MVC integration_

## Quick Example ##
Resources are define by POJOs and the JAX-RS @Path, @GET, @PUT Java annotations. For example:

```
@Path("/library")
public class Library {

   @GET
   @Path("/books")
   public String getBooks() {...}

   @GET
   @Path("/book/{isbn}")
   public String getBook(@PathParam("isbn") String id) {
      // search my database and get a string representation and return it
   }

   @PUT
   @Path("/book/{isbn}")
   public void addBook(@PathParam("isbn") String id, @QueryParam("name") String name) {...}

   @DELETE
   @Path("/book/{id}")
   public void removeBook(@PathParam("id") String id {...}   
}
```

The @Path annotation is not limited to simple path expressions. You also have the ability to insert regular expressions into @Path's value. For example:
```
@Path("/resources)
public class MyResource {

   @GET
   @Path("{var:.*}/stuff")
   public String get() {...}
}
```