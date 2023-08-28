Definition: In binary search, the idea of the algorithm is to divide and conquer, reducing the search area by half each time, trying to find a target number.
	In order to leverage this power however, our array must first be sorted, else we cannot make assumptions about the array's contents.

In pseudo-code:

Repeat until the (sub)array is of size 0:
	
Calculate the middle point of the current (sub)array.
If the target is at the middle, stop.

Otherwise, if the target is less than what's at the middle, repeat, 
changing the end point to be just to the left of the middle.

Otherwise, if the target is greater than what's at the middle,
repeat, changing the start point to be just to the right of the middle.

Ο(log n) Worst-case scenario: We have to divide a list of n elements
in half repeatedly to find the target element, either because the target element will be found at the end of the last division or doesn't exist in the array at all.

Ω(1) Best-case scenario : The target element is at the midpoint of the full array, and so we can stop looking immediately after we start.

#Search #BigONotation 