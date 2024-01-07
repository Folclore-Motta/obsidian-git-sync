Class method is marked with a `@classmethod` [[Decorator]] is a built-in function decorator that is an expression that gets evaluated after your function is defined.

A class method receives the class as an implicit first argument, just like an [[Instance Method]] receives the instance. Instead of receiving a [[self]] parameter, class methods take a [[cls]] parameter that points to the class --and not the object instance-- when the method is called.

```Python
Syntax Python Class Method:

class C(object):
    @classmethod
    def fun(cls, arg1, arg2, ...):
       ...

```

```Python
class MyClass:

@classmethod
def classmethod(cls):
	return 'class method called', cls

print(MyClass.classmethod())

```


Because the class method only has access to this [[cls]] argument, it can't modify object instance state. That would require access to [[self]]. However, class methods can still modify class state that applies across all instances of the class.  

# Resume

- A class method is a method that is bound to the [class](https://www.geeksforgeeks.org/python-classes-and-objects/) and not the object of the class.
- They have the access to the state of the class as it takes a class parameter that points to the class and not the object instance.
- It can modify a class state that would apply across all the instances of the class. For example, it can modify a class variable that will be applicable to all the instances.
# **When to use the class method?**

 We generally use the class method to create factory methods. Factory methods return class objects ( similar to a constructor ) for different use cases.

```Python
# Python program to demonstrate
# use of class method and static method.
from datetime import date
 
 
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
 
    # a class method to create a Person object by birth year.
    @classmethod
    def fromBirthYear(cls, name, year):
        return cls(name, date.today().year - year)
 
    # a static method to check if a Person is adult or not.
    @staticmethod
    def isAdult(age):
        return age > 18
 
 
person1 = Person('mayank', 21)
person2 = Person.fromBirthYear('mayank', 1996)
 
print(person1.age)
print(person2.age)
 
# print the result
print(Person.isAdult(22))
```

Another way to look at this use of class methods is that they allow you to define alternative constructors for your classes.

Python only allows one [[Constructor `__init__`]] method per class. Using class methods it’s possible to add as many alternative constructors as necessary. This can make the interface for your classes self-documenting (to a certain degree) and simplify their usage.

