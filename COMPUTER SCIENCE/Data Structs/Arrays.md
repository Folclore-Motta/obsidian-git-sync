## Definition
An array is basically a block of memory allocated in the [[Memory Stack]] divided by the size of indexes that the program specified which is divided by the [[Primitive Data Type]] specified.
- char_(1 byte each block)
- int(4 or 8 bytes)
- float(4 or 8 bits)
- ...
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



