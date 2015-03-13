# Introduction #

This is a stub article for [Spray](http://spray.cc/), a lightweight Scala framework for building RESTful web services on top of Akka.

_From the [Spray wiki](http://spray.cc/):_

It sports the following main features:

  * Completely asynchronous, non-blocking, actor-based request processing for efficiently handling very high numbers of concurrent connections
  * Powerful, flexible and extensible internal Scala DSL for declaratively defining your web service behavior
  * Immutable model of the HTTP protocol, decoupled from the underlying web server / servlet container
  * Full testability of your REST services, without the need to fire up containers or actors

Apart from a server module spray also has a client component for easy consumption of REST APIs (spray-client) and a JSON module (spray-json).