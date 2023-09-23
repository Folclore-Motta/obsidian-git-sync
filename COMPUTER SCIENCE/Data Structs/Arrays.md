## Definition

An array is basically a block of memory allocated in the [[Memory Stack]] divided by the size of indexes that the programmer specified in the creation which is divided by the [[Primitive Data Type]].

For example we could set an array of 10 integers that will be a total of 40 bytes
```C
	int integers[10];
```

- char_(1 byte each block)
- int(4 or 8 bytes)
- float(4 or 8 bits)
- ...

To access each one of those indexes we use the `[]` notation which we will specify by an number which one do you want to access like `[3]` in that case.

We have to remember that in **C** the name of the array is a [[Pointers|Pointer]] that points to itself, but specifically to the first index also know as `[0]`.

Basically `*(integers)` is equal to `[0]`

So in resume an array is a pointer 
## Properties

- Insertion is bad - lots of shifting to fit an element in the middle
- Deletion is bad - lots of shifting after removing an element
- Lookup is great - random access, constant time
- Relatively easy to sort
- Relatively small size-wise
- Stuck with a fixed size, no flexibility

## Application
Example:
 ```C
 int array[50];
 ```



