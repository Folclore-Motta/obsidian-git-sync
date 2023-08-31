Structures provide a way to unify several variables of different types into a single, new variable [[Defining Custom Data Types|type]] which can be assigned its own type name.

We use structures(structs) to group together elements of a variety of data types that have a logical connection

Think of a structure like a "super-variable".

Once we have defined a structure, wich we typically do in a separate .h files or atop our programs outside of any functions, we have effectively created a new type.

That means we can create variables of that type using the familiar syntax.

We can also access the various **fields** (also known as **members**) of the structure using the dot operator(*.*)

## Consume and Memory Space



Structures are created in the [[Memory Stack]] but we can [[Dynamic Memory Allocation|Dynamically Allocate ]] then creating then into the [[Memory Heap]]. We can dynamically allocate structures at run time if your program requires it.

In order to access the fields of your structures in that situation we first need to dereference the pointer to the structure, and then we can access its fields.

That syntax of deference a **field** of a struct is not very clean so we have an specific syntax for that it's the arrow operator -> that does the same as (*value).field