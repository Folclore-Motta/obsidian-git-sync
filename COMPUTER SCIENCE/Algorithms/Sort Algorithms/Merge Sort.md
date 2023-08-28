In merge sort, the idea of the algorithm is to sort smaller arrays
and them combine those arrays together (merge them) in sorted order.

Merge sort leverages something called recursion

In pseudo-code:
	Sort the left half of the array ( assuming n > 1)
	Sort the right half of the array (assuming n > 1)
	Merge the two halves together


Ο(n log n) Worst-case scenario: We have to split n elements up and then recombine them, effectively doubling the sorted sub-arrays as we build them up. (combining sorted 1-element arrays into 2-element arrays, combining sorted 2-element arrays into 4-element arrays...).

Ω(n log n) Best-case scenario : The array is already perfectly sorted. But we still have to split and recombine it back together with this algorithm.


#Algorithms #BigONotation