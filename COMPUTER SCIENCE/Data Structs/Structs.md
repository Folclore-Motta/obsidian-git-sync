Structures provide a way to unify several variables of different types into a single, new variable type which can be assigned its own type name.

We use structures(structs) to group together elements of a variety of data types that have a logical connection

Think of a structure like a "super-variable".

Once we have defined a structure, wich we typically do in a separate .h files or atop our programs outside of any functions, we have effectively created a new type.

That means we can create variables of that type using the familiar syntax.

We can also access the various **fields** (also known as **members**) of the structure using the dot operator(*.*)

## Application

## The ways of declaring a struct

The simple way of doing it:

```C
struct Point {
    double x;
    double y;
};
```

We could apply a sugar syntax here to, avoid writing construct every time using [[Defining Custom Data Types| typedef]]:

```typedef struct Point Point;```

Now `struct Point` is known as only `Point` as simple as that

We could also create an anonymous struct but it implicates 
// IMPLICATES INTO SOME THINGS

```C
typedef struct {
    double x;
    double y;
}Point;
```

But we could simply even more doing the two things at same time with this syntax

```C
typedef struct Point {
    double x;
    double y;
} Point;
```

## Memory

Structures are created in the [[Memory Stack]] but we can [[Dynamic Memory Allocation|Dynamically Allocate ]] then creating then into the [[Memory Heap]]. We can dynamically allocate structures at run time if your program requires it.

In order to access the fields of your structures in that situation we first need to dereference the pointer to the structure, and then we can access its fields.

That syntax of deference a **field** of a struct is not very clean so we have an specific syntax for that it's the arrow operator -> that does the same as (*value).field
- First, it dereferences the pointer on the left side of the operator.
- Second, it accesses the field on the right side of the operator.

