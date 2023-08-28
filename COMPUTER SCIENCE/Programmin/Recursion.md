Every recursive function has two cases that could apply, given any input, otherwise it will run forever or until it crashes because because you run out of memory segmentation fault;
	The base case, which when triggered will terminate the recursive process.
	The recursive case, which is where the recursion will actually occur.

This forms the basis for a recursive definition of the factorial function.

```C
fact(n) = n * fact(n-1)

int fact(int n)
{
	//Base case
	if (n == 1)
	{
		return 1;
	}
	else
	{
		return n * fact(n-1);
		/*
		Recursive Case
		fact(1) = 1
		fact(2) = 2 * fact(1)
		fact(3) = 2 * fact(2)
		fact(4) = 2 * fact(3)
		fact(5) = 2 * fact(4)
		...
		*/
	}
}
```

In general, but not always, recursive functions replace loops in non-recursive functions.

It's also possible to have more than one base or recursive case, if the program might recurse or terminate in different ways, depending on the input being passed in.

Multiple base cases: The Fibonacci number sequence is defined as follows:
	The first element is 0;
	The second element is 1.
	The nth element is the sum of the (n-1)th and the (n-2)th elements.

Multiple recursive cases: The Collatz conjecture.

The Collatz conjecture is applies to positive integers and speculates that it is always possible to get "back to 1" if you follow these steps;
	if n is 1, stop
	Otherwise, if n is even, repeat this process on n/2.
	Otherwise, if n is odd, repeat this process on 3n + 1.

```C
int collatz(int number)
{
	// Base case
	if (number == 1)
		return 0;
	
	// Even numbers
	else if ((number % 2) == 0)
		return 1 + collatz(number/2);
	
	// Odd numbers
	else
		return 1 + collatz(3 * number + 1);
}
```


To a better acknowledgment of how the functions will perform in memory see [[Call Stacks]].

