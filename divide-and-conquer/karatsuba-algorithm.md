# Karatsuba algorithm

Given two binary strings that represent value of two integers, find the product of two strings. For example, if the first bit string is “1100” and second bit string is “1010”, output should be 120.

For simplicity, let the length of two strings be same and be n.

A **Naive Approach** is to follow the process we study in school. One by one take all bits of second number and multiply it with all bits of first number. Finally add all multiplications. This algorithm takes O(n^2) time.\


![product](https://media.geeksforgeeks.org/wp-content/uploads/fastmultiplication-e1518461987241.jpg)

Using **Divide and Conquer**, we can multiply two integers in less time complexity. We divide the given numbers in two halves. Let the given numbers be X and Y.

For simplicity let us assume that n is even&#x20;

```
X =  Xl*2^(n/2) + Xr    [Xl and Xr contain leftmost and rightmost n/2 bits of X]
Y =  Yl*2^(n/2) + Yr    [Yl and Yr contain leftmost and rightmost n/2 bits of Y]
```



The product XY can be written as follows:&#x20;

```
XY = (Xl*2^(n/2) + Xr)(Yl*2^(n/2) + Yr)
   = 2^n XlYl + 2^(n/2)(XlYr + XrYl) + XrYr
```

If we take a look at the above formula, there are four multiplications of size n/2, so we basically divided the problem of size n into four sub-problems of size n/2.&#x20;

But that doesn’t help because solution of recurrence T(n) = 4T(n/2) + O(n) is O(n^2). The tricky part of this algorithm is to change the middle two terms to some other form so that only one extra multiplication would be sufficient. The following is tricky expression for middle two terms. &#x20;

```
XlYr + XrYl = (Xl + Xr)(Yl + Yr) - XlYl- XrYr
```

So the final value of XY becomes &#x20;

```
XY = 2^n XlYl + 2^(n/2) * [(Xl + Xr)(Yl + Yr) - XlYl - XrYr] + XrYr
```

With above trick, the recurrence becomes T(n) = 3T(n/2) + O(n) and solution of this recurrence is O(n1.59).

_What if the lengths of input strings are different and are not even?_ To handle the different length case, we append 0’s in the beginning. To handle odd length, we put _floor(n/2)_ bits in left half and _ceil(n/2)_ bits in right half. So the expression for XY changes to following. &#x20;



```
XY = 2^( 2 ceil(n/2)) XlYl + 2^(ceil(n/2)) * 
     [(Xl + Xr)(Yl + Yr) - XlYl - XrYr] + XrYr
```
