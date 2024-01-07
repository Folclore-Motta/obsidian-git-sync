
A static method does not receive an implicit first argument.
neither [[self]] nor [[cls]]

The Static Method, `MyClass.staticmethod` was marked with a `@staticmethod` [[Decorator]] to flag it as a static method.

This type of method takes neither a [[self|self]] nor a [[cls]] parameter (but of course it's free to accept an arbitrary number of parameters).

```Python
Syntax Python Static Method: 

class C(object):
    @staticmethod
    def fun(arg1, arg2, ...):
        ...
returns: a static method for function fun.
```

```Python
class MyClass:

@staticmethod
	def staticmethod():
		return 'static method called'

obj = MyClass()
```

Therefore a static method can neither modify object state or class state. Static methods are restricted in what data they can access - and they're primarily a way to [[Namespace]] your methods.

```Python
	print(obj.staticmethod())
	print(Myclass.staticmethod())
```

Behind the scenes Python simply enforces the access restrictions by not passing in the [[self]] or the [[cls]] argument when a static method gets called using the dot syntax.

This confirms that static methods can neither access the object instance state nor the class state. They work like regular functions but belong to the class’s (and every instance’s) [[Namespace]].

In general, static methods know nothing about the class state. They are utility-type methods that take some parameters and work upon those parameters. On the other hand class methods must have class as a parameter.