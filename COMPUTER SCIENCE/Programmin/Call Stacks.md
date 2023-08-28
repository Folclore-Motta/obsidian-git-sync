When you call a function, the system sets aside space in memory for that function to do its necessary work.
	We frequently call such chunks of memory **stack** frames or function frames

More than one function's stack frame may exist in memory at given time. If `main()` calls `move()`, which then calls `direction()`, all three functions have open frames. But just one of these frames you be active despite the fact that all of three of them will have space aside.

These frames are arranged in a **stack** [[Memory Stack]] The frame frame for the most recently called function is always on the top of the stack.

When a new function is called, a new frame is **pushed** onto the top of the stack and becomes the active frame.

When a function finishes its work, its frame is **popped** off of the stack, and the frame immediately below it becomes the new, active, function on the top of the stack. This function picks up immediately where it left off.

As an example we gonna use a mathematical concept using [[Recursion]]

```C
int fact(int n)
{
	if (n == 1)
		return 1;
	else
		return n * fact(n-1);
}

int main(void)
{
	printf("%i\n", fact(5));
}
```


|Stack| |
|-------| - | 
|Main()| |
|printf()| |
|fact(5)| |
|fact(4)| |
|fact(3)| |
|fact(2)| |
|fact(1)| |


#ComputerScience #ProgramminLogic