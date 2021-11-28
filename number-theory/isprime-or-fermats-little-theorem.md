# IsPrime | Fermat's Little Theorem



Given a number n, check if it is prime or not. We have introduced and discussed the School method for primality testing.\


In this page, Fermat’s method is discussed. This method is a probabilistic method and is based on Fermat’s Little Theorem.

**Fermat's little theorem:**

```
If n is a prime number, then for every a, 1 < a < n-1,

an-1 ≡ 1 (mod n)
 OR 
an-1 % n = 1 
 

Example: Since 5 is prime, 24 ≡ 1 (mod 5) [or 24%5 = 1],
         34 ≡ 1 (mod 5) and 44 ≡ 1 (mod 5) 

         Since 7 is prime, 26 ≡ 1 (mod 7),
         36 ≡ 1 (mod 7), 46 ≡ 1 (mod 7) 
         56 ≡ 1 (mod 7) and 66 ≡ 1 (mod 7) 

```

If a given number is prime, then this method always returns true. If the given number is composite (or non-prime), then it may return true or false, but the probability of producing incorrect results for composite is low and can be reduced by doing more iterations.

Below is algorithm:&#x20;

```
// Higher value of k indicates probability of correct
// results for composite inputs become higher. For prime
// inputs, result is always correct
1)  Repeat following k times:
      a) Pick a randomly in the range [2, n - 2]
      b) If gcd(a, n) ≠ 1, then return false
      c) If an-1 &nequiv; 1 (mod n), then return false
2) Return true [probably prime].
```
