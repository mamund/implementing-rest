# Introduction #

Ramone is a C# client side library that simplifies access to HTTP based Web APIs and REST services. It has a strong focus on REST and implements elements of the Uniform Interface as first class citizens of the API.

This means natural support for

  * URIs as identifiers for resources.
  * The standard HTTP methods GET, POST, PUT and more.
  * Multiple media types (XML, JSON, HTML, ATOM and more).
  * User defined media types.
  * Hyper media controls (linking and key/value forms).

What Ramone does is to wrap the inner workings of HTTP and make encoding and decoding easier through the use of codecs for the various formats used on the web.

# Details #

Ramone supports plain XML, JSON, and Atom out of the box, but where it really excels is when it comes to working with user defined objects, domain specific media types and hyper media elements.

In its most simple form you can transfer an object like this:

```
  class Cat
  {
    public string Name { get; set; }
    public DateTime Born { get; set; }
  }

  RamoneRequest req = Session.Bind(CatUrlTemplate, new { id = 8 });

  Cat c = req.Get<Cat>().Body;
```

Hyper media elements for linking resources together can be added with objects that implement `ILink` (such as the built-in `AtomLink`):

```
  class Cat
  {
    public string Name { get; set; }
    public DateTime Born { get; set; }
    public AtomLink Parent { get; set; }
  }
```

Links can be followed to other resources like this:

```
  RamoneRequest req = Session.Bind(CatUrlTemplate, new { id = 8 });

  Cat c = req.Get<Cat>().Body;

  Cat parent = c.Body.Parent.Follow().Get<Cat>().Body;
```


# Source code #

See https://github.com/JornWildt/Ramone