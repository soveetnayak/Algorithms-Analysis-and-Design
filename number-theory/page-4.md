# Page 4



GCD (Greatest Common Divisor) or HCF (Highest Common Factor) of two numbers is the largest number that divides both of them.&#x20;

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/GCD-or-HCF-of-two-numbers-1024x512.png)

Attention reader! All those who say programming isn't for kids, just haven't met the right mentors yet. Join the [** **](https://practice.geeksforgeeks.org/courses/first-step-to-dsa/)[**Demo Class for First Step to Coding Course**](https://practice.geeksforgeeks.org/courses/first-step-to-coding-demo/)**, **specifically **designed for students of class 8 to 12. **\


The students will get to learn more about the world of programming in these **free classes** which will definitely help them in making a wise career choice in the future.

For example GCD of 20 and 28 is 4 and GCD of 98 and 56 is 14. **For solution**  suppose a=98 & b=56 &#x20;

\
\


a>b so put a= a-b and b is  remain same  so  a=98-56=42  & b= 56 . Now b>a  so  b=b-a and  a is same&#x20;

b= 56-42 = 14 & a= 42   . 42 is  3 times of 14  so **HCF** is 14  . likewise  a=36  & b=60  ,here b>a                        so b = 24 & a= 36  now a>b so a= 12 & b= 24  . 12 is HCF of 36 and 60 .  This  concept  is  always  satisfying.&#x20;

[Recommended: Please solve it on “_**PRACTICE**_ ” first, before moving on to the solution.](https://practice.geeksforgeeks.org/problems/lcm-and-gcd/0) \
&#x20;

&#x20;A **simple solution** is to [find all prime factors](https://www.geeksforgeeks.org/print-all-prime-factors-of-a-given-number/) of both numbers, then find intersection of all factors present in both numbers. Finally return product of elements in the intersection.\
An **efficient solution **is to use [Euclidean algorithm ](https://www.geeksforgeeks.org/euclidean-algorithms-basic-and-extended/)which is the main algorithm used for this purpose. The idea is, GCD of two numbers doesn’t change if smaller number is subtracted from a bigger number.&#x20;

* C++
* C
* Java
* Python3
* C#
* PHP
* Javascript

| `// C++ program to find GCD of two numbers#include <iostream>using` `namespace` `std;// Recursive function to return gcd of a and bint` `gcd(int` `a, int` `b){    // Everything divides 0    if` `(a == 0)       return` `b;    if` `(b == 0)       return` `a; ` `    // base case    if` `(a == b)        return` `a; ` `    // a is greater    if` `(a > b)        return` `gcd(a-b, b);    return` `gcd(a, b-a);} ` `// Driver program to test above functionint` `main(){    int` `a = 98, b = 56;    cout<<"GCD of "<<a<<" and "<<b<<" is "<<gcd(a, b);    return` `0;}` |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

**Output: **

```
GCD of 98 and 56 is 14
```
