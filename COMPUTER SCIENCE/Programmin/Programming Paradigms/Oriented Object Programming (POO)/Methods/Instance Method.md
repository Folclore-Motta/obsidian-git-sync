## Definition

Methods are basically [[Functions]] that exist inside a class and can only be called by an instance of that class by the syntax of `class.method_name()` where method_name is the name of your method the method can ask for arguments just like functions do, but in the definition of the method you have to always pass and argument the [[self]] argument.

It has the same has the same features of the functions like non mandatory parameters by pre-defining it.

```Python
class Item:
	def calculate_total_price(self, x, y):
		return x * y
```


Instance methods can also access the class itself through the `self.__class__` [[Class Attribute]]. This makes instance methods powerful in terms of access restrictions - they can modify state on the object instance _and_ on the class itself.

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