# Page 2



Given a number n, check if it is prime or not. We have introduced and discussed School and Fermat methods for primality testing.\
[Primality Test | Set 1 (Introduction and School Method)](https://www.geeksforgeeks.org/primality-test-set-1-introduction-and-school-method/) \
[Primality Test | Set 2 (Fermat Method)](https://www.geeksforgeeks.org/primality-test-set-2-fermet-method/)\
In this post, the Miller-Rabin method is discussed. This method is a probabilistic method ( like Fermat), but it is generally preferred over Fermat’s method.

**Algorithm:**

Attention reader! Don’t stop learning now. Get hold of all the important DSA concepts with the [**DSA Self Paced Course**](https://practice.geeksforgeeks.org/courses/dsa-self-paced) at a student-friendly price and become industry ready.  To complete your preparation from learning a language to DS Algo and many more,  please refer [**Complete Interview Preparation Course**](https://practice.geeksforgeeks.org/courses/complete-interview-preparation)**.**

In case you wish to attend **live classes **with experts, please refer [**DSA Live Classes for Working Professionals **](https://practice.geeksforgeeks.org/courses/geeks-classes-live)and [**Competitive Programming Live for Students**](https://practice.geeksforgeeks.org/courses/competitive-programming-live).

```
// It returns false if n is composite and returns true if n
// is probably prime.  k is an input parameter that determines
// accuracy level. Higher value of k indicates more accuracy.
bool isPrime(int n, int k)
1) Handle base cases for n < 3
2) If n is even, return false.
3) Find an odd number d such that n-1 can be written as d*2r. 
   Note that since n is odd, (n-1) must be even and r must be 
   greater than 0.
4) Do following k times
     if (millerTest(n, d) == false)
          return false
5) Return true.

// This function is called for all k trials. It returns 
// false if n is composite and returns true if n is probably
// prime.  
// d is an odd number such that d*2r = n-1 for some r>=1
bool millerTest(int n, int d)
1) Pick a random number 'a' in range [2, n-2]
2) Compute: x = pow(a, d) % n
3) If x == 1 or x == n-1, return true.

// Below loop mainly runs 'r-1' times.
4) Do following while d doesn't become n-1.
     a) x = (x*x) % n.
     b) If (x == 1) return false.
     c) If (x == n-1) return true. 
```

**Example:**&#x20;

\
\


```
Input: n = 13,  k = 2.

1) Compute d and r such that d*2r = n-1, 
     d = 3, r = 2. 
2) Call millerTest k times.

1st Iteration:
1) Pick a random number 'a' in range [2, n-2]
      Suppose a = 4

2) Compute: x = pow(a, d) % n
     x = 43 % 13 = 12

3) Since x = (n-1), return true.

IInd Iteration:
1) Pick a random number 'a' in range [2, n-2]
      Suppose a = 5

2) Compute: x = pow(a, d) % n
     x = 53 % 13 = 8

3) x neither 1 nor 12.

4) Do following (r-1) = 1 times
   a) x = (x * x) % 13 = (8 * 8) % 13 = 12
   b) Since x = (n-1), return true.

Since both iterations return true, we return true. 
```
