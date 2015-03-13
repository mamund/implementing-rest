# Introduction #
This is a stub article on the [Jersey](http://wikis.sun.com/display/Jersey/Main) framework


# Jersey #
_From [Overview of JAX-RS 1.0 Features](http://wikis.sun.com/display/Jersey/Overview+of+JAX-RS+1.0+Features)_

Jersey is Sun's production quality reference implementation for JSR 311: JAX-RS: The Java API for RESTful Web Services. Jersey implements support for the annotations defined in JSR-311, making it easy for developers to build RESTful web services with Java and the Java JVM.

### Sample ###
_From Sun's [RESTful Web Services Developer's Guide](http://docs.sun.com/app/docs/doc/820-4867/ggnxo?l=en&a=view)_

The following code sample is a very simple example of a root resource class using JAX-RS annotations. The sample shown here is from the samples that ship with Jersey, and which can be found in the following directory of that installation:
```
jersey/samples/helloworld/src/main/java/com/sun/jersey/samples/helloworld/resources/HelloWorldResource.java.

package com.sun.jersey.samples.helloworld.resources;

import javax.ws.rs.GET;
import javax.ws.rs.Produces;
import javax.ws.rs.Path;

// The Java class will be hosted at the URI path "/helloworld"
@Path("/helloworld")
public class HelloWorldResource {
    
    // The Java method will process HTTP GET requests
    @GET
    // The Java method will produce content identified by the MIME Media
    // type "text/plain"
    @Produces("text/plain")
    public String getClichedMessage() {
        // Return some cliched textual content
        return "Hello World";
    }
}

```