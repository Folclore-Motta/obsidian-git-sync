Hash table is a very important Data Structure Widely used

Let's imagine that we have an array of 11 elements


0 -> 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7 -> 8 -> 9 -> 10

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

Imagine that we want to insert Zoe and we calculate the index for Zoe but we see that Zoe is already occupied. We can apply some techniques to resolve this problem it depends of the situation

### Linear Probing

We see that the place that Zoe should occupy it's already taken. So we move to the _next index_ and see that it's also occupied so we repeat the process and go to the _next index_ again and we see that's open so we insert the value there.

In pseudo-code:
- Hash the value that we want to insert.
- Go to the index that correspond to the result number of the hash function.
- Until the value is not inserted
	- If it's occupied
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

<li style="margin-right:10px;">Elemento 7</li>

<li style="margin-right:10px;">Elemento 8</li>

<li style="margin-right:10px;">Elemento 9</li>

<li>Elemento 10</li>

</ul>

So finding the value later will also involve [[Linear Search]] since the value will not be exactly as it supposed, but closer we just need to move up some values and then we will find the value that we are searching for.

$$

Load\ Factor = \frac{Total\ number\ of\ itens\ stored}{Size\ of\ the\ Array}

$$