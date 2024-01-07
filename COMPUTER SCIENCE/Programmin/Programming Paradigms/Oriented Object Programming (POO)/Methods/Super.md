Super alone returns a temporary object of the superclass that then allows you to call that superclass's methods.

Calling the previously built methods with super(). saves you from needing to rewrite those methods in your subclass, and allows you to swap out superclasses with minimal code changes.

super() in Single Inheritance: 

```Python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

    def perimeter(self):
        return 2 * self.length + 2 * self.width

class Square:
    def __init__(self, length):
        self.length = length

    def area(self):
        return self.length * self.length

    def perimeter(self):
        return 4 * self.length

square = Square(4)
print(square.area())
rectangle = Rectangle(2,4)
print(rectangle.area())
```

Here, there are two similar classes: `Rectangle` and `Square`.

In this example, you have two shapes that are related to each other: a square is a special kind of rectangle. The code, however, doesn’t reflect that relationship and thus has code that is essentially repeated.

By using inheritance, you can reduce the amount of code you write while simultaneously reflecting the real-world relationship between rectangles and squares:

```Python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):

    def perimeter(self):
        return 2 * self.length + 2 * self.width

# Here we declare that the Square class inherits from the Rectangle class
class Square(Rectangle):
    def __init__(self, length):
        super().__init__(length, length)
```

Here, you’ve used `super()` to call the [[Constructor `__init__`]] of the `Rectangle` class passing the required arguments in that case , allowing you to use it in the `Square` class without repeating code. Below, the core functionality remains after making changes:

```Python
square = Square(4)
print(square.area())
rectangle = Rectangle(2,4)
print(rectangle.area())
```

When you run this, even though your `Square` class doesn’t explicitly implement it, the call to `.area()` will use the `.area()` method in the superclass and print `16`. The `Square` class **inherited** `.area()` from the `Rectangle` class.

## What Can `super()` Do for You?

So what can `super()` do for you in single inheritance?

Like in other object-oriented languages, it allows you to call methods of the superclass in your subclass. The primary use case of this is to extend the functionality of the inherited method.

In the example below, you will create a class `Cube` that inherits from `Square` and extends the functionality of `.area()` (inherited from the `Rectangle` class through `Square`) to calculate the surface area and volume of a `Cube` instance:

```Python
class Square(Rectangle):
    def __init__(self, length):
        super().__init__(length, length)

class Cube(Square):
    def surface_area(self):
        face_area = super().area()
        return face_area * 6

    def volume(self):
        face_area = super().area()
        return face_area * self.length
```

**Caution**: Note that in our example above, `super()` alone won’t make the method calls for you: you have to call the method on the proxy object itself.

Here you have implemented two methods for the `Cube` class: `.surface_area()` and `.volume()`. Both of these calculations rely on calculating the area of a single face, so rather than re-implementing the area calculation, you use `super()` to extend the area calculation.

Also notice that the `Cube` class definition does not have an `.__init__()`. Because `Cube` inherits from `Square` and `.__init__()` doesn’t really do anything differently for `Cube` than it already does for `Square`, you can skip defining it, and the `.__init__()` of the superclass (`Square`) will be called automatically.

`super()` returns a delegate object to a parent class, so you call the method you want directly on it: `super().area()`.

Not only does this save us from having to rewrite the area calculations, but it also allows us to change the internal `.area()` logic in a single location. This is especially in handy when you have a number of subclasses inheriting from one superclass.

## A `super()` Deep Dive

Before heading into multiple inheritance, let’s take a quick detour into the mechanics of `super()`.

While the examples above (and below) call `super()` without any parameters, `super()` can also take two parameters: the first is the subclass, and the second parameter is an object that is an instance of that subclass.

First, let’s see two examples showing what manipulating the first [variable](https://realpython.com/python-variables/) can do, using the classes already shown:

```Python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

    def perimeter(self):
        return 2 * self.length + 2 * self.width

class Square(Rectangle):
    def __init__(self, length):
        super(Square, self).__init__(length, length)
```

In Python 3, the `super(Square, self)` call is equivalent to the parameterless `super()` call. The first parameter refers to the subclass `Square`, while the second parameter refers to a `Square` object which, in this case, is `self`. You can call `super()` with other classes as well:

```Python
class Cube(Square):
    def surface_area(self):
        face_area = super(Square, self).area()
        return face_area * 6

    def volume(self):
        face_area = super(Square, self).area()
        return face_area * self.length
```

In this example, you are setting `Square` as the subclass argument to `super()`, instead of `Cube`. This causes `super()` to start searching for a matching method (in this case, `.area()`) at one level above `Square` in the instance hierarchy, in this case `Rectangle`.

In this specific example, the behavior doesn’t change. But imagine that `Square` also implemented an `.area()` function that you wanted to make sure `Cube` did not use. Calling `super()` in this way allows you to do that.

**Caution:** While we are doing a lot of fiddling with the parameters to `super()` in order to explore how it works under the hood, I’d caution against doing this regularly.

The parameterless call to `super()` is recommended and sufficient for most use cases, and needing to change the search hierarchy regularly could be indicative of a larger design issue.

**What about the second parameter? Remember, this is an object that is an instance of the class used as the first parameter. For an example, `isinstance(Cube, Square)` must return `True`.

By including an instantiated object, `super()` returns a **bound method**: a method that is bound to the object, which gives the method the object’s context such as any instance attributes. If this parameter is not included, the method returned is just a function, unassociated with an object’s context.

For more information about bound methods, unbound methods, and functions, read the Python documentation [on its descriptor system](https://docs.python.org/3.7/howto/descriptor.html).

