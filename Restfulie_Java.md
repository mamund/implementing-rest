# Introduction #

Restfulie second supported language was Java.
While most frameworks up to Restfulie's release allowed users to create Restful systems, Restfulie forced users to adopt a Restful approach.

You can see Restfulie's features at http://restfulie.caelum.com.br

# Client Example #

The following example shows how to execute a POST and further delete requests:

```
Order order = new Order();

// place the order
order = service("http://www.caelum.com.br/order").post(order);

// cancels it
resource(order).getTransition("cancel").execute();
```

# Server Example #

The following example shows how an order can be configured to contain both a self and cancel relations. This will automatically add support to resource representations as xml, and json, for example:

```
public class Order implements StateResource {

	public List<Transition> getFollowingTransitions(Restfulie control) {
		if (status.equals("unpaid")) {
			control.transition("self").uses(OrderingController.class).get(this);
			control.transition("cancel").uses(OrderingController.class).cancel(this);
		}
		return control.getTransitions();
	}

}

```