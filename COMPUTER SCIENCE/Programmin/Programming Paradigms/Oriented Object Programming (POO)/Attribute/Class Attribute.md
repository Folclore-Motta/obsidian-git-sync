## Definition

#TODO better construct this resuming the code to only changes...

A class attribute is a Python variable that belongs to a class rather than a particular object. It’s shared between all the objects of this class and is defined outside the constructor function, `__init__(self,...)`, of the class.

The below `ExampleClass` is a basic Python class with two attributes: `class_attr` and `instance_attr`. 

```Python
class ExampleClass(object):
  class_attr = 0

  def __init__(self, instance_attr):
    self.instance_attr = instance_attr
```

- `instance_attr` is an [[Instance Attribute]] defined inside the constructor.
- `class_attr` is a class attribute defined outside the constructor.

The `instance_attr` is only accessible from the [[Scope]] of an object. The class attribute (`class_attr`) is accessible as both a property of the class and as a property of objects, as it’s shared between all of them.

```Python
if __name__ == '__main__':

foo = ExampleClass(1)
bar = ExampleClass(2)

    # print the instance attribute of the objects foo, bar
    print (foo.istance_attr)
    print (bar.instance_attr)
    
    # print the class attribute of the class ExampleClass
    # the class itself as a property of the class Itself
    print (ExampleClass.class_attr)
    
    # print the class attribute  of the class as a proporty of the 
    # objects foo, bar
    print (bar.class_attr)
    print (foo.class_attr)
    
    # try to print instance attribute as a class property
    print (ExampleClass.instance_attr)
	#AttributeError: type object 'ExampleClass' has no 
	#attribute'instance_attr'
```

Notice that the class attribute can be accessed as a class property and as an [[Instance]] property, however, accessing an instance attribute as a class property raises an `AttributeError`.

Behind the scenes, it's a game of [[Namespace| namespaces]]. In python, a [[namespace]] is a mapping between objects and names. To keep it simple, let's say it's a Python dictionary that represents a key to the name of the object 

Python classes and objects have different namespaces. For our example, we have `ExampleClass.__dict__` as a message for our class, 
and `foo.__dict__(bar.__dict__)` as a namespace for our object foo(bar).

```Python
if __name__ = '__main__':
	foo = ExampleClass(1)
	bar = ExampleClass(2)
	
	print str(ExampleClass.__dict__)
	print str(foo.__dict__)
	print str(bar.__dict__)
```

When you access an attribute (instance or class attribute) as a property of an object using the dot convention, it searches first in the namespace of that object for that attribute name. If it’s found, it returns the value. Otherwise, it searches in the namespace of the class. If nothing is found there, it raises an  `AttributeError`. The object namespace is before the class namespace.

If we find, in one class, both an instance attribute and a class attribute with the same name, the access to that name from your object will get you the value in the object namespace. Below is a simplified version of the lookup [function](https://builtin.com/data-science/python-wrapper).

```Python
def instlookup(inst, name):
    ## simplified algorithm...
    if inst.__dict__.has_key(name):
        return inst.__dict__[name]
    else:
        return inst.__class__.__dict__[name]
```

When you access an attribute as a class property, it searches directly in the class namespace for the name of that attribute. If it’s found, it returns the value. Otherwise, it raises an [[AttributeError]].

## Class Attributes Mutate Into Instance Attributes

It might seem weird, but class attributes do mutate to become instance attributes. Let’s consider the following scenario.

```Python
if __name__ == '__main__':
	foo = ExampleClass(1)
	bar = ExampleClass(2)

    #print the class attribute as a porperty of a foo
    print foo.class_attr
    #0
    #modify the class attribute as a foo property
    foo.class_attr = 5
    print foo.class_attr
    #5
    #print the class attribute as a porperty of a bar
    print bar.class_attr
    # 0 
    #oups !!!!
```

The `class_attr` is shared between all the objects of the class. However, when we change the value from the foo object, this change is not visible from the `bar` object, which still has the old value, `0`, rather than the new value, `5`. Let’s check our namespaces and try to understand what’s happening.

```Python
if __name__ = '__main__':
 foo = ExampleClass(1)
    bar = ExampleClass(2)


    print str(foo.__dict__)
    #{'instance_attr': 1} the namespace of the foo object had only his instance attribute
    print foo.class_attr 
    #0
    foo.class_attr = 5
    print str(foo.__dict__)
    '''{'instance_attr': 1, 'class_attr': 5} once the affectation is done 
    on the class attribute from the object foo , it is added as an instance attribute 
    in his namespace
    ''' 
```

​The affectation added a new instance attribute to the object `foo`, and only to that object, which is why in the previous example the object `bar` kept printing the class attribute.

With immutable objects, this behavior is always the same. However, with mutable objects like lists, for example, it’s not always the case and depends on how you modify your class attribute.

Let’s change our previous class to have a list as a class attribute.

```Python
class ExampleClass(object):
  class_attr = []

  def __init__(self, instance_attr):
    self.instance_attr = instance_attr
```

We modify that list as a property of the object `foo` by appending a new element to it.

```Python
if __name__ = '__main__':
 foo = ExampleClass(1)
    bar = ExampleClass(2)

    #print the class attribute as a porperty of a foo
    print foo.class_attr
    # []
    #modify the class attribute as a foo property
    foo.class_attr.append(0)
    print foo.class_attr
    #[0]
    #print the class attribute as a porperty of a bar
    print bar.class_attr
    # [0] 
```

​When a mutable class attribute is modified by an object, it does not mutate into an instance attribute for that object. It stays shared between all the objects of the class with the new elements appended to it.

However, if you attach a new list to that attribute (`foo.class_attr = list("foo")`), you’ll get the same behavior as the immutable objects. 

```Python
if __name__ = '__main__':
 foo = ExampleClass(1)
    bar = ExampleClass(2)

    #print the class attribute as a porperty of a foo
    print foo.class_attr
    # []
    #modify the class attribute as a foo property
    foo.class_attr = list("example") 
    print foo.class_attr
    #[e,x,a,m,p,l,e]
    #print the class attribute as a porperty of a bar
    print bar.class_attr
    # [] 
```

You can compare the namespaces on your own as proof of the previous behavior.

The takeaway is that Python class attributes may be useful in different cases, however, they must be used with caution in order to avoid unexpected behaviors.