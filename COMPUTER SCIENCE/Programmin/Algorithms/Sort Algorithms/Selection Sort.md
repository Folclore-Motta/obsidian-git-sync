Definition: In selection sort, the idea of the algorithm is to find the smallest unsorted element and add it to the end of the sorted list.

In pseudo-code:
	Repeat until no unsorted elements remain:
		Search the unsorted part of the data to find the smallest value
		Swap the smallest found value with the first element of the unsorted part
		Now that that this value is indeed the first element of our array we can ignore it and jump next to the right value n-1 every interaction


Ο(n²) Worst-case scenario:  We have to iterate over each of the n elements of the array (to find the smallest unsorted element) and we must repeat this process n times, since only one element gets sorted on each pass.

Ω(n²) Best-case scenario: Exactly the same! There's no way to guarantee the array is sorted until we go through this process for all the elements.


#Algorithms #BigONotation