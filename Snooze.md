# Introduction #
This article is a stub for the Snooze framework.

# Snooze #
_From the [project wiki](http://www.assembla.com/wiki/show/dKAZuYVVSr3lc5abIlDkbG):_

ASP.NET MVC is far too reliant on magic-strings. Snooze is a thin layer on top of the ASP.NET MVC framework that brings some sanity back!
Snooze makes URLs a first-class, strongly-typed concept. Controllers contain methods that handle HTTP requests for URLs.

Snooze is still under development, but the following samples are from working code.

Enjoy!

### In Global.asax, routes are mapped using strongly-typed expressions ###
```
routes.Map<BooksUrl>(b => "books");
routes.Map<BookUrl>(b => "book/" + b.BookId); // route will be "book/{BookId}"
routes.Map<BookCommentsUrl>(c => "comments"); // route will be "book/{BookId}/comments"
```
### Those expressions reference these Url classes. ###
Notice that BookCommentsUrl is a SubUrl of BookUrl. This means is has access to BookUrl via its Parent property.
```
public class BooksUrl : Url { }

public class BookUrl : Url
{
    public string BookId { get; set; }
}

public class BookCommentsUrl : SubUrl<BookUrl> { }
```

### A single controller class can handle requests for any of these Urls. ###
Dispatch is done using the request HTTP method.
```
public class BookController : ResourceController
{
    public ActionResult Get(BooksUrl url)
    {
        var books = LoadBooksXml();
        // Notice how we can construct URLs directly...
        var links = from book in books.Element("catalog").Elements("book")
                    select new BookUrl { BookId = book.Attribute("id").Value };
 
        return OK(new BooksViewModel
        {
            BookLinks = links.ToArray()
        });
    }
 
    public ActionResult Get(BookUrl url)
    {
        var books = LoadBooksXml();
        var book = books.Element("catalog").Elements("book").FirstOrDefault(e => e.Attribute("id").Value == url.BookId);
        return OK(new BookViewModel
        {
            Author = book.Element("author").Value,
            Title = book.Element("title").Value
        });
    }
 
    public ActionResult Post(BookCommentsUrl url, string comment)
    {
        // Can access book id using: url.Parent.BookId
        throw new NotImplementedException();
    }
 
    private XDocument LoadBooksXml()
    {
        return XDocument.Load(Server.MapPath("~/App_Data/Books.xml"));
    }
}
public class BooksViewModel
{
    public BookUrl[] BookLinks { get; set; }
}
 
public class BookViewModel
{
    public string Author { get; set; }
    public string Title { get; set; }
}
```