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

Rather than storing just one value we can consider a key:value approach when each one of the values has pairs for example **Ada** would be the key and her date of birth the corresponding value, for this reason a hash table key value pairs is referred as **Hash Map**. 

# Collisions 

Imagine that we want to inset Zoe if we calculate the index for Zoe
We see that the place that Zoe should occupy it's already taken. So we move to the _next index_ and see that it's also occupied so we repeat the process and go to the _next index_ again and we see that's open so we insert the value there.

Let's take another example with 

