# GCD



GCD (Greatest Common Divisor) or HCF (Highest Common Factor) of two numbers is the largest number that divides both of them.&#x20;

Let us find the GCD of 36 and 60.

We know,

* 36 = 2 \* 2 \* 3 \* 3
* 60 = 2 \* 2 \* 3 \* 5

When we collect all the commen factors, ie 2 \* 3 \* 3, we get the GCD as 12.

For example GCD of 20 and 28 is 4 and GCD of 98 and 56 is 14.&#x20;

**For solution**  suppose a=98 & b=56 &#x20;

a>b so put a= a-b and b is  remain same  so  a=98-56=42  & b= 56 . Now b>a  so  b=b-a and  a is same&#x20;

b= 56-42 = 14 & a= 42   . 42 is  3 times of 14  so **HCF** is 14  . likewise  a=36  & b=60  ,here b>a                        so b = 24 & a= 36  now a>b so a= 12 & b= 24  . 12 is HCF of 36 and 60 .  This  concept  is  always  satisfying.&#x20;

&#x20;A **simple solution** is to find all prime factors of both numbers, then find intersection of all factors present in both numbers.&#x20;

Finally, return the product of elements in the intersection.

\
An **efficient solution** is to use Euclidean algorithm which is the main algorithm used for this purpose. The idea is, GCD of two numbers doesn’t change if smaller number is subtracted from a bigger number.&#x20;

```cpp
// Recursive function to return gcd of a and b
int gcd(int a, int b){    
// Everything divides 0    
if (a == 0)       
return b;    
if (b == 0)       
return a;      
// base case    
if (a == b)        
return a;      
// a is greater    
if (a > b)        
return gcd(a-b, b);    
return gcd(a, b-a);}  
// Driver program to test above function
int main(){    
int a = 98, b = 56;    
cout<<"GCD of "<<a<<" and "<<b<<" is "<<gcd(a, b);    
return 0;}
```

**Output:**&#x20;

```
GCD of 98 and 56 is 14
```
