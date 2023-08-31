When we program we have to pass through a lot of steps and some of them might repeat which is pretty normal, but repeating code it's not a good thing. Because turn out that our become more buggy, less readable and can lost performance.

To solve this problem we can use a **function** for example:
Imagine that we want to get three values from the user and validated if all of those values are higher than 5.

Instead of writing the code repeatedly three times we can abstract this ideia and call it by a name like valid_user_input():
```C
bool valid_user_input(int x):
	if (x > 5)
		return 0;
	return 1;

if (valid_user_input(x))
	printf("Valid Input");
```


**bool** is the value that the function return in that case is a boolean.
**valid_user_input** is the name of the function
**int x** is the type and the argument of the function.
**return** is a instruction that make the function return the specified value that can be used in operations or stored in a variable

In this example we used a function C which have some interesting aspects.


In C the functions cannot have predefine values but in languages like python it can be possible

```
print("Test", n='!')
```

We changed the default value of n in this case that are and `"\n"` to __!__ 