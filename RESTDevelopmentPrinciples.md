# Introduction #
This is a set of statements about the nature of development environments that encourage REST-ful implementations. Right now it's a hodge-podge of notes and ideas. Feel free to suggest changes and modifications; challenge assumptions, etc.

# Basic Traits #
Development tools that enable a REST-style result:
  * Encourage application implementations as a collection of RESOURCES on a server (i.e. programming using a resource object)
  * Encourage the use of CACHING (making it easy to express and interpret caching directives for both client and server)
  * Encourage STATELESS interactions between client and server (making it hard to store transient state on the server, easy to store transient state on the client)
  * Encourage using a UNIFORM INTERFACE (with clearly defined semantics) for interacting with RESOURCES (programming using a limited set of public methods that follow protocol rules)
  * Encourage using a LAYERED SYSTEM as an implementation principle (making it easy to add authentication, caching, CDNs, etc. without re-writing existing code)
  * Encourage using CODE-ON-DEMAND to safely extend functionality at runtime (support servers sending scripts and plug-ins to clients, support accepting and executing plug-ins and scripts safely on the client)

In addition, the development environment should:
  * Encourage the use of SELF-DESCRIPTIVE messages through:
    * Clear separation between control-data (HTTP Headers) and message bodies
    * Dependence (and ease of use) on media-types
    * Full and easy control of caching directives (including automatic marking of GET responses based on configuration information)
  * Encourage implementing resources as REPRESENTATIONS (using media-types to express resource representations) through:
    * Ability to mark resources and methods as supportive of one or more media types
    * Easy access to serialization/transformation of resource data into media-type compliant representations
    * Ability to determine the beset match representation format (media type) for the client (e.g. support for server-driven and/or agent-driven content negotiation)
  * Encourage implementing RESOURCE IDENTIFIERS (using URI mapping to match request URIs to server-side code)
  * Encourage hypermedia to power application state (including mutually-agreed upon annotated links and link templates in the representations)