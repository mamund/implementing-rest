# Introduction #

This article is a stub

Here are a few approaches that should be explored here:
  * Focus on human-readable documentation
  * Focus on media-type definition
  * Focus on implementing support for OPTIONS
  * Others?

# Documenting REST-ful Applications #

## Human Readable Documentation ##
_From Chapter 14 of [RESTful Web Services Cookbook](http://www.restful-webservices-cookbook.org) by [Subbu Allamaraju](http://www.subbu.org/about) w/ contributions by [Mike Amundsen](http://amundsen.com/)_

Fully describe the following in human readable documentation.

  * All resources, and methods supported for each resource.
  * Media types and representation formats for resources in requests and responses.
  * Each link relation used, its business significance, HTTP method to be used, and resource that the link identifies.
  * All fixed URIs that are not supplied via links.
  * Query parameters used for all fixed URIs.
  * URI templates, and token substitution rules.
  * Authentication and security credentials for accessing resources.

For XML representations, if your clients and servers are capable of supporting XML schemas, use a schema language as a “convention” to describe the structure of XML documents used for representations in requests and responses. For other formats, use conventions to describe representations in prose.