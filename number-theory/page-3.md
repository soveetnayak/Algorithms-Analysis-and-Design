# Page 3



Given a positive integer, check if the number is prime or not. A prime is a natural number greater than 1 that has no positive divisors other than 1 and itself. Examples of first few prime numbers are {2, 3, 5, \
**Examples :** \
&#x20;

```
Input:  n = 11
Output: true

Input:  n = 15
Output: false

Input:  n = 1
Output: false
```

&#x20;

Attention reader! Don’t stop learning now. Get hold of all the important DSA concepts with the [**DSA Self Paced Course**](https://practice.geeksforgeeks.org/courses/dsa-self-paced) at a student-friendly price and become industry ready.  To complete your preparation from learning a language to DS Algo and many more,  please refer [**Complete Interview Preparation Course**](https://practice.geeksforgeeks.org/courses/complete-interview-preparation)**.**

In case you wish to attend **live classes **with experts, please refer [**DSA Live Classes for Working Professionals **](https://practice.geeksforgeeks.org/courses/geeks-classes-live)and [**Competitive Programming Live for Students**](https://practice.geeksforgeeks.org/courses/competitive-programming-live).

[Recommended: Please solve it on “_**PRACTICE**_” first, before moving on to the solution.](https://practice.geeksforgeeks.org/problems/prime-number/0)

**School Method **\
A simple solution is to iterate through all numbers from 2 to n-1 and for every number check if it divides n. If we find any number that divides, we return false. \
Below is the implementation of this method. \
&#x20;

* C++
* Java
* Python3
* C#
* PHP
* Javascript

| `// A school method based C++ program to check if a// number is prime#include <bits/stdc++.h>using` `namespace` `std;` `bool` `isPrime(int` `n){    // Corner case    if` `(n <= 1)  return` `false;` `    // Check from 2 to n-1    for` `(int` `i=2; i<n; i++)        if` `(n%i == 0)            return` `false;` `    return` `true;}` `// Driver Program to test above functionint` `main(){    isPrime(11)?  cout << " true\n": cout << " false\n";    isPrime(15)?  cout << " true\n": cout << " false\n";    return` `0;}` |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

**Output :** \
&#x20;

```
true
false
```

Time complexity of this solution is O(n)\
**Optimized School Method **\
We can do following optimizations:&#x20;

1. Instead of checking till n, we can check till √n because a larger factor of n must be a multiple of smaller factor that has been already checked.
