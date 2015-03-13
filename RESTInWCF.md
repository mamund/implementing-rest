# Introduction #

This article is a stub for Microsoft's REST In WCF framework.

# Details #
_From the [Overview of REST in WCF page](http://msdn.microsoft.com/en-us/netframework/dd547388.aspx):_

Windows Communication Foundation (WCF), part of the .NET Framework, provides the first unified programming model for rapidly building service-oriented applications. It enables the development of secure, reliable, transacted services that interoperate with current Microsoft investments and non-Microsoft platforms.

With the .NET Framework 3.5 release, WCF added support for building REST style services. REST, an architectural style for building distributed hypermedia driven applications, involves building resource-oriented services by defining resources that implement uniform interfaces using standard HTTP verbs (GET, POST, PUT, and DELETE), and that can be located/identified by a URI.

REST support within WCF was enhanced with the release of .NET Framework 3.5 SP1 to add make REST development easier and to support the ADO.NET Entity Framework entities in WCF contracts. Improvements were made around UriTemplate flexibility and the Visual Studio tooling to increase developer productivity.

# REST WCF Starter Kit #

_From the [WCF REST Starter Kit](http://www.asp.net/downloads/starter-kits/wcf-rest/) home page._

The first set of features in the starter kit is server-side features for building WCF REST services, which enable or simplify various aspects of using the REST capabilities in WCF. These include declarative caching, security, error handling, help page support, conditional PUT, push style streaming, type based dispatch and semi-structured XML support. This functionality is exercised by a set of Visual Studio templates for creating REST services such as an Atom Feed service, a REST-RPC hybrid service, a resource singleton or collection service, and an Atom Publishing Protocol service.

The second set of features is client-side features for accessing WCF and third-party REST services from within .Net applications. The new HttpClient class provides the REST developer with a uniform extensible model for sending HTTP requests and processing HTTP responses, in a variety of formats. The new "Paste Xml as Type" Visual Studio add-in enhances the serialization support in HttpClient by generating serializable types based on XML examples or XSD schema.