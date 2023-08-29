	- Calculation applied to a key to transform it into an address
	- For numeric keys, divide the key by the number of available addresses, n and take the reminder address = key Mod n
	- For alphanumeric keys, divide the sum of ASCII codes in a key by the number of available addresses, n, and take the remainder
	- Folding method divides key into equal parts then adds the parts togheter 
		- The telephone number 01452 8345654, becomes 01 + 45 + 28 + 34 + 56 + 54 = 218
		- Depeding on the size of table, may then divide by some constant and take remainder.

Collisions 

