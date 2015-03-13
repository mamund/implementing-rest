# Introduction #
This is a stub for the Exyus framework

_From the [Exyus project home page](http://code.google.com/p/exyus/):
## Features ##
The current version of **Exyus** has the following features:
  * Resource-oriented coding - you create inbound endpoints by creating resource classes
  * Built-in support for standard HTTP Methods (GET,HEAD,PUT,POST,DELETE,OPTION as resource methods)
  * Url-Mapping - Resource classes can support multiple Uri patterns (via regular expressions)
  * Multiple Representations - The same resource can support any number of Content Types (XML, JSON, Atom, HTML, etc.)
  * Caching Support - Mark your resource to support Validation and/or Expiration caching
  * Authentication - Supports Digest and Basic Auth
  * Authorization - Map Urls and HTTP Methods for user access
  * Compression - Automatically supports gzip/deflate per client headers.
  * Built-in HTTPClient - Perform direct HTTP requests against other HTTP servers._

## Quick Example ##
Using the **Exyus** engine means you can define a read/write resource that allows live editing (tested w/ [Amaya](http://www.w3.org/Amaya/) browser) with just the following C# code:
```
using System;
using Exyus.Web;

namespace Exyus.Editable
{
    // full read/write via PUT w/ ETags
    [UriPattern(@"/editable/(?<docid>[^/?]*)?(?:\.xcs)(?:[?])?(?:.*)?")]
    [MediaTypes("text/html","application/json","application/atom+xml")]
    public class editPages : XmlFileResource
    {
        public editPages()
        {
            this.ContentType = "text/html";
            this.UpdateMediaTypes = new string[] { "text/html" };
            this.AllowPost = false;
            this.AllowCreateOnPut = true;
            this.DocumentsFolder = "~/documents/editable/";
            this.StorageFolder = "~/storage/editable/";
            this.XHtmlNodes = new string[] { "//body" };
            this.LocalMaxAge = 600;
            this.ImmediateCacheUriTemplates = new string[]
                {
                    "/editable/.xcs",
                    "/editable/{docid}.xcs"
                };
        }
    }

}
```