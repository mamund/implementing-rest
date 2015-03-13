This is a page for recording authoritative quotes that answer commonly asked questions.  If you come across a quote from a well known REST advocate that addresses a frequent question, please add it here.


---

### Does a service have to implement the PUT and DELETE methods to be considered RESTful? ###

> In any case, there are plenty of RESTful services that do nothing but GET and POST. The key is how those methods are used, not what methods are used. To give a specific example, what makes a wiki more or less RESTful is almost always determined by how it (ab)uses GET and sessions -- whether it uses PUT or POST for editing pages is sugar topping in comparison.

Roy Fielding (http://tech.groups.yahoo.com/group/rest-discuss/message/10746)


---

### Does /resource.xml and /resource.json refer to the same resource? ###

Here is an excerpt from an mailing list post:

> >  But in hindsight, what's the difference between

```
GET /resource.xml  
GET /resource.json  
```
> > and

```
GET /resource
Accept: application/xml

GET /resource
Accept: application/json
```


> The former are requests on two different resources. The latter are two varying requests on one resource. The only difference, in my opinion, is that the single varying resource makes for a better bookmark because it is less susceptible to both differences in user agent capabilities (different accept lists) and changes in supported media types over time. It is not, however, a replacement for the media-specific resources and their corresponding URIs.

Roy Fielding (http://tech.groups.yahoo.com/group/rest-discuss/message/13960)


---

### Is it better to use the query string or the path for explicitly requesting a format in an URL? ###

According to Roy:

> I don't know of any sane system that uses the query portion to distinguish format-specific resources. Everybody uses name extensions for that purpose.

http://tech.groups.yahoo.com/group/rest-discuss/message/11153