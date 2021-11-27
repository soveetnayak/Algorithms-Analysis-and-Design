# Page 1



Given a number n, check if it is prime or not. We have introduced and discussed the School method for primality testing in Set 1.\
[Primality Test | Set 1 (Introduction and School Method)](https://www.geeksforgeeks.org/primality-test-set-1-introduction-and-school-method/)\
In this post, Fermat’s method is discussed. This method is a probabilistic method and is based on Fermat’s Little Theorem.

```
Fermat's Little Theorem:
If n is a prime number, then for every a, 1 < a < n-1,

an-1 ≡ 1 (mod n)
 OR 
an-1 % n = 1 
 

Example: Since 5 is prime, 24 ≡ 1 (mod 5) [or 24%5 = 1],
         34 ≡ 1 (mod 5) and 44 ≡ 1 (mod 5) 

         Since 7 is prime, 26 ≡ 1 (mod 7),
         36 ≡ 1 (mod 7), 46 ≡ 1 (mod 7) 
         56 ≡ 1 (mod 7) and 66 ≡ 1 (mod 7) 

Refer this for different proofs.
```

If a given number is prime, then this method always returns true. If the given number is composite (or non-prime), then it may return true or false, but the probability of producing incorrect results for composite is low and can be reduced by doing more iterations.

Attention reader! Don’t stop learning now. Get hold of all the important DSA concepts with the [**DSA Self Paced Course**](https://practice.geeksforgeeks.org/courses/dsa-self-paced) at a student-friendly price and become industry ready.  To complete your preparation from learning a language to DS Algo and many more,  please refer [**Complete Interview Preparation Course**](https://practice.geeksforgeeks.org/courses/complete-interview-preparation)**.**

In case you wish to attend **live classes **with experts, please refer [**DSA Live Classes for Working Professionals **](https://practice.geeksforgeeks.org/courses/geeks-classes-live)and [**Competitive Programming Live for Students**](https://practice.geeksforgeeks.org/courses/competitive-programming-live).

Below is algorithm:&#x20;

\
\


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
