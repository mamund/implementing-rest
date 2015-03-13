# Introduction #

This is a stub article for [BlueEyes](https://github.com/jdegoes/blueeyes), a lightweight Web 3.0 framework for Scala, featuring a purely asynchronous architecture, extremely high-performance, massive scalability, high usability, and a functional, composable design.

_From the [BlueEyes readme](https://github.com/jdegoes/blueeyes#readme):_

BlueEyes has been used in production across large clusters of instances deployed in Amazon EC2, reliably handling tens of thousands of requests a second, in an environment with 24x7 uptime requirements (online display advertising).

The framework has been designed to meet the following requirements:

  * Stateless design, to achieve massive scalability;
  * Purely asynchronous request handling, to achieve extremely fast per-instance performance;
  * Highly composable, modular design that minimizes bloat and surface area of the API;
  * Declarative service construction;
  * Support for continuous deployment and automated testing;
  * Idiomatic Scala interfaces to highly-scalable databases such as MongoDB.

BlueEyes does not have any features for server-side generation of HTML, CSS, or Java[.md](.md)Script. BlueEyes does not (natively) serve static files, like Apache or Jetty. BlueEyes is intended only for creating RESTful web services that are consumed by clients (such as browsers or servers).

Those looking for a traditional model/view web framework for the Scala programming language are directed to the [Lift](http://liftweb.net) Web Framework.