# Factorial



Factorial of a non-negative integer, is multiplication of all integers smaller than or equal to n.&#x20;

For example factorial of 6 is&#x20;

6\*5\*4\*3\*2\*1 which is 720.\
&#x20;

**Recursive Solution:** \
Factorial can be calculated using following recursive formula. \
&#x20;

```
  n! = n * (n-1)!
  n! = 1 if n = 0 or n = 1
```

&#x20;Factorial of 5 is 120

**Iterative Solution:** \
Factorial can also be calculated iteratively as recursion can be costly for large numbers. Here we have shown the iterative approach using both for and while loop.&#x20;

\
**Using For loop**&#x20;

```
#include <iostream>
using namespace std; 
// function to find factorial of given number
unsigned int factorial(unsigned int n)
{    
    int res = 1, i;
    for (i = 2; i <= n; i++)
        res *= i;
    return res;
} 
// Driver code
int main()
{    
    int num = 5;
    cout << "Factorial of "         << num << " is "         << factorial(num) << endl;
    return 0;
}
```

**Output :** \
&#x20;

```
Factorial of 5 is 120
```

\
**One line Solution :**

```
#include <iostream>
using namespace std; 
int factorial(int n)
{    
// single line to find factorial
    return (n == 1 || n == 0) ? 1 : n * factorial(n - 1);} 
// Driver Code
int main()
{
    int num = 5;
    cout << "Factorial of " << num << " is "<< factorial(num);
    return 0;
} 
```

**Output:**&#x20;

```
Factorial of 5 is 120
```
