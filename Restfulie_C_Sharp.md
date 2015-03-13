# Introduction #

Restfulie's third language support was C#.
While most frameworks up to Restfulie's release allowed users to create Restful systems, Restfulie forced users to adopt a Restful approach.

You can see Restfulie's features at http://restfulie.caelumobjects.com/restfulie_features

Currently Restfulie supports only the client side with support to C#.

# Client Example #

The following example shows how to execute a GET, POST and further delete requests

```
//retrieves the resource through GET: the entry point
dynamic order = Restfulie.At(resourceURI).Get();

Console.WriteLine("the order price is " + order.Price);
Console.WriteLine("The order product is" + order.Product);


//  Executing a state transition:
order.Pay();	


// sends a delete request
order.Cancel()

```