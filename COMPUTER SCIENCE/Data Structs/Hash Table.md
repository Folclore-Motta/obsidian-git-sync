Hash table is a very important Data Structure Widely used to index large amounts of data
Addresses of each key calculated using the key itself
Collisions resolve with open or closed addressing 
Insertion, deletion and retrieval occur in constante time
Let's imagine that we have an array of 6 elements



<ul style="list-style-type:none; display:flex;">

<li style="margin-right:10px;" >Index<br>0</li>

<li style="margin-right:10px;">Index 1</li>

<li style="margin-right:10px;">Index 2</li>

<li style="margin-right:10px;">Index 3</li>

<li style="margin-right:10px;">Index 4</li>

<li style="margin-right:10px;">Index 5</li>

<li style="margin-right:10px;">Index 6</li>
</ul>

To calculate the value of a data we have multiple ways In this case let's use an string as example with the string: "Mia".

First we sum all of the letters by it's ANSCII code;
Mia M 77 i 107 a 97 = 279 

Therefore we divide the result by quantity of elements in the array in that case there are 11
279 / 11 = 4.

The result of the operation will be the index in the array that mia will be put on in that case is position 4.

In that case the formula is:
Index number = __sum ASCII codes__ *Mod* __size of array__

We call this formula a Hash Algorithm and there a lot of different [[Hashing Algorithm]].

So let's say we want to find Ada let's do the same calculation
Ada = (65 + 100 + 97) = 262 Mod 11 = 9

Then we use the calculate value to perform the a fast array look up
myData = Array(9);

Rather than storing just one value we can consider a key:value approach when each one of the values has pairs for example **Ada** would be the key and her **date of birth** the corresponding value, for this reason a hash table key value pairs is referred as **Hash Map**. 

# Collisions 

## Open Addressing 
- Linear Probing
- Plus 3 rehash
- Quadratic probing (failed attempts)²
- Double Hashing

Imagine that we want to insert Zoe and we calculate the index for Zoe but we see that Zoe is already occupied. We can apply some techniques to resolve this problem it depends of the situation

### Linear Probing

We see that the place that Zoe should occupy it's already taken. So we move to the _next index_ and see that it's also occupied so we repeat the process and go to the _next index_ again and we see that's open so we insert the value there.

In pseudo-code:
- Hash the value that we want to insert.
- Go to the index that correspond to the result number of the hash function.
- Until the value is not inserted
	- If it's occupiedser we just need to move up some values and then we will find the value that we are searching for.

		- Move to the next value
	- Else
		- put the value in that index. 

In resume if the index is already occupied we have to move one index up seeing if the element is free if it is we put the value there basically using [[Linear Search]] for that.

<ul style="list-style-type:none; display:flex;">

<li style="margin-right:10px;" >Elemento 0</li>

<li style="margin-right:10px;">Elemento 1</li>

<li style="margin-right:10px;">Elemento 2</li>

<li style="margin-right:10px;">Elemento 3</li>

<li style="margin-right:10px;">Elemento 4</li>

<li style="margin-right:10px;">Elemento 5</li>

<li style="margin-right:10px;">Elemento 6</li>
</ul>


So finding the value later will also involve [[Linear Search]] since the value will not be exactly as it supposed, but close. 

The ratio of the data is know as the Load Factor it could be used to make the array resizable by knowing when Load Factor reached a certain threshold
$$

Load\ Factor = \frac{Total\ number\ of\ itens\ stored}{Size\ of\ the\ Array}

$$

But in Ideal word every value stored would be in his respective index exactly calculated avoiding collisions making our hash table O(1) to find a value trough. But at the cost of processing to generate the unique output trough the [[Hashing Algorithm]] or needing more memory to deal with more indexes.

Closed addressing

Avoiding collision at all

## Chaining

It's the same concept that we have addressed before but this time using [[Linked Lists]]
Let's take "Mia" again as an example again

