Definition: In linear search, the idea of the algorithm is to iterate across
the array from left to right, searching for a specified element.

In pseudo-code?
	Repeat, stating at the first element.
		If the first element is what you're looking for (the target), stop.
		Otherwise, move to the next element.

Ο(n) Worst-case scenario: We have to look trough the entire array of n elements, either because the target element is the last element of the array or doesn't exist in the array at all.

Ω(1) Best-case scenario : The target element is the first element of the array, and so we can stop looking immediately after we start.


#Search #BigONotation 