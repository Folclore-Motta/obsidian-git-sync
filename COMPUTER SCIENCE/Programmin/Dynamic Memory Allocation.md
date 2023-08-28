What if we don't know how much memory our program we'll need at compile-time?
How do we get access to new memory while our program is running?

We can use pointers to get access to a block of dynamically-allocated memory at runtime.

Dynamically allocated memory comes from a pool of memory known as the [[Memory Heap]].

Prior to this point, all memory we've been working with has been coming from a pool of memory known as the [[Memory Stack]]


Related: [[Memory Management]]

We get this dynamically-allocated memory by making a call to the C standard library function ```malloc()```, passing as its parameter the number of bytes requested.

After obtaining memory for you (if it can), ```malloc()``` will return a pointer to that memory.

What if ```malloc()``` can't give you memory? It'll hand you back NULL. Because of that if have to always check if the value returned equals NULL
```C
// Statically obtain an integer
int x;

// dynamically obtain an integer
int *px = malloc(sizeof(int));

// get an integer from the user
int x = get_int();
// Array of floats on the stack
float stack_array[x];
// array of floats on the heap
float *heap_array = malloc(x * sizeof(float));
if (heap_array == NULL)
{
	exit(EXIT_FAILURE);
}
```

Here's the trouble: Dynamically allocated memory is not automatically return to the system for later use when the function in which it's created finishes execution.

Failing to return memory back to the system when you're finished with it results in a memory leak which can compromise your system's performance.

When you finish working with dynamically-allocated memory, you must ```free()``` it.
```C
char *word = malloc(50 * sizeof(char));

// do stuff with the word

// Then you free it
free(word);
```

Three golden rules:
	1. Every block of memory that you ```malloc()``` must subsequently be ```free()```d.
	2. Only memory that you ```malloc()``` should be  ```free()```d.
	3. Do not free() a block of memory more than once.

```C
int m;
int *a;
// Getting memory from the heap
int *b = malloc(sizeof(int));
if (b == NULL)
{
	return 1;
}
/* One of the differences of asking memory from the stack and the heap
is that we cannot acess the memory directly we must dereference the pointer to acess it*/

// Now a has the address of m inside of it
a = &m; 
/* both are pointers so "a" will receive the value of "b" Which is an address therefore "a" will point to the same address as "b"*/
a = b; 
m = 10;
*b = m + 2;
// *b = 12
free(b);

// Once you free memory you cannot use it anymore
*a = 11;
// Will probably result in a segmentation fault. Strange things might result
```