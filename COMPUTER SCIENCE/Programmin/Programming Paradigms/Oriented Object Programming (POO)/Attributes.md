# Definition 

Atributes work just like variables, but the difference is that all atributes inside of a class are related.

There are two ways of creating attributes in different scenarios 
and user cases:

**First way:**

```Python
Class Example:
	pass

Example.attribute = "valor"
print(Example.attribute)
```

We instanced the **Class** value and then assigned a attribute with the string type value = "valor". this is useful when we want to created and extra attribute inside a class but only want that attribute in the specific instance.

**Second way:**

```Python
Class Example:
	def __init__(self):
	self.attribute = "valor"

instance = Example()
print(insta.attribute)
```

Another way is by creating it inside the class prefixed with self
and the difference by previous method was that doing in that way every instance of that class that we create will already come with this attribute by definition.

Notice that we have to use the [[Constructor `__init__`]] to set those variables for us.

And the [[self]] keyword that refers to the instance name