The init constructor is a [[Methods|Magic Method]] that inicialize a Class by executing the block of code that's inside of the `__init__` method every time that you instanced a class.

```Python
class Item:
	def __init__(self, name):
		print(f"I am an instance of {name}")

item1 = Item("Phone")
item2 = item("Notebook")
``` 

If you see the output you can see that the function print execute when class is instanced the class.

Another feature that the `__init__` method has is defining the [[Primitive Data Type | Data Type]] that the class expect by adding the syntax of `argument: data type`

Example:

```Python
Class Item:
	def __init__(self, name: str, price: float, quantity=0)
		self.name = name
		self.price = price
		self.quantity = quantity
	
	def total_price(self, x, y)
		return x * y
```

The **quantity** argument has type integer but it's not required to specify since we pre-defined it as 0. Python understands that it's an integer type argument.

But still not enough the a good practice is to also check the values passed than their data type using assert making sure that everything is fine and controlled.

