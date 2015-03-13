# Introduction #

This is a stub article for [Pinky](https://github.com/pk11/pinky/wiki), a REST/MVC Glue Web Framework for Scala.

_From the [Pinky wiki](https://github.com/pk11/pinky/wiki):_

> Pinky is a Scala REST/MVC glue web framework built on top of Guice and Guice Servlet 2.0.

> ## Features ##
    * No custom template language
    * (almost) No XML configuration
    * URL/template mapping is convention based but can be easily overwritten
    * Form generator/validator
    * Jdbc helper
    * akka integration
    * scheduler for akka jobs
    * comet integration (based on jetty7 continuation , note it does not require a jetty container though)
    * Out of the box support for the following representations:
      * XML (via xstream or scala)
      * JSON (via xstream or json lib)
      * RSS 2.0
      * FreeMarker
      * Velocity
    * Controllers are plain old servlets
    * Filters are implemented as plain old filters
    * Filters/Servlet creation and mapping are managed by Guice
    * Out of the box support for REST via managed servlets
    * AOP support for servlet/filters and for regular components (via Guice)
    * No learning curve (we are dealing with plain old servlets/filters after all)
    * Dependency injection (powered by Guice)
    * Scoped components ie Request, Session, custom scopes (powered by Guice)
    * Ease access to other Guice modules like warp-persist for db persistance
    * Easy access to Request/Response objects
    * Easy to integrate with existing projects (thanks to servlets)
    * Easy to extend
    * new API to deal with jdbc
    * support for form generation and validation