# Introduction #
This article is a stub.

_From documentation at the [project home](http://webmachine.basho.com/)._

# Details #
This ... documents the basic mechanics of Webmachine from the point of view of a single incoming HTTP Request, documenting the behavior of Webmachine through to the HTTP Response.

(This is a bit different from what you might get with a "Web Framework" as we're not going to talk about MVC, ORMs, or anything else about the rest of the shape of your application. We believe that you know better than we do how to structure your own app -- Webmachine's job is to make sure that your app's presence on the Web is well-behaved and well-structured.)

When a request is initially received by Webmachine it is handled by the dispatcher. If the dispatcher does not find a matching resource then it will immediately respond with a 404 Not Found. If a match is found then a request data record is created and the matching resource is kicked off via its init/1 function.

The resource then flows through the decision core, which is effectively just running the request through the HTTP flowchart. At each decision point (diamond) in the diagram, Webmachine will determine which path to follow. In some cases it can determine the path purely from the request data -- for instance, the path from decision C3 depends purely on whether the client sent an Accept header. In many cases, however, the decision is application-specific -- the path from B10 depends on the value the resource returns from allowed\_methods. Eventually the chosen path will terminate at one of the rectangles on the diagram. At that point Webmachine will send an appropriate HTTP response, with the headers and body dependent on the path through the diagram and the values returned by the resource's functions.