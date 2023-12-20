
# Definition

Self refers to the instance itself when we declare item = Item():

We are passing self as argument even if we don't declare it. It will become clear with an example

```Python
Class Item:
	def __init__(self, name, price, quantity)
		self.name = name
		self.price = price
		self.quantity = quantity
	
	def total_price(self, x, y)
		return x * y

item = Item("Phone", 100, 10)
print(item.total_price(100, 10))
```

As you can see the [[Constructor `__init__`]] and every other [[Methods]]
that we create inside of a class requires a **self** argument but it's not passed direct inside the brackets. The self argument is passed when we instanced the class as the name of the instance. Just to exemplify it would be like this

```Python
Class Item:
	def __init__(item, name, price, quantity)
		item.name = name
		item.price = price
		item.quantity = quantity
	
	def total_price(item, x, y)
		return x * y

item = Item()
```

And if we created other instance called banana we would substitute every **self** argument value for banana.

Another aspect of self is that the [[Attributes]] that we have inside the class are available trough the whole class so we don't have to ask for them in the parameters like we did in the `total_price()` method.

```Python
Class Item:
	def __init__(self, name, price, quantity)
		self.name = name
		self.price = price
		self.quantity = quantity
	
	def total_price(self, x, y)
		return self.quantity * self.price
		
item = Item("Phone", 100, 10)
print(item.total_price())
```

