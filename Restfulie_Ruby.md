# Introduction #

Restfulie first version was released in Ruby and supporting Rails on the server side.
While most frameworks up to Restfulie's release allowed users to create Restful systems, Restfulie forced users to adopt a Restful approach.

You can see Restfulie's features at http://restfulie.caelumobjects.com/restfulie_features

# Client Example #

The following example shows how to execute a GET, POST and further delete requests

```
order = Order.from_web resource_uri

puts "Order price is #{order.price}"

# sends a post request to create a payment
order.pay payment

# sends a delete request
order.cancel
```

# Server Example #

The following example shows how an order can be configured to contain both a self, cancel and payment relations. This will automatically add support to resource representations as xml, json and atom:

```
class Order
  acts_as_restfulie |order, t|
    t << :self, {:action => :show}
    t << :pay, {:action => :create, :controller => :payment }
  end
end
```