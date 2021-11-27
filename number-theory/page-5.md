# Page 5



Factorial of a non-negative integer, is multiplication of all integers smaller than or equal to n. For example factorial of 6 is 6\*5\*4\*3\*2\*1 which is 720.\
&#x20;

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/program-for-factorial-of-a-number-1024x512.png)

Attention reader! All those who say programming isn't for kids, just haven't met the right mentors yet. Join the [** **](https://practice.geeksforgeeks.org/courses/first-step-to-dsa/)[**Demo Class for First Step to Coding Course**](https://practice.geeksforgeeks.org/courses/first-step-to-coding-demo/)**, **specifically **designed for students of class 8 to 12. **\


The students will get to learn more about the world of programming in these **free classes** which will definitely help them in making a wise career choice in the future.

**Recursive Solution:** \
Factorial can be calculated using following recursive formula. \
&#x20;

\
\


```
  n! = n * (n-1)!
  n! = 1 if n = 0 or n = 1
```

&#x20;

[Recommended: Please solve it on “_**PRACTICE**_ ” first, before moving on to the solution.](https://practice.geeksforgeeks.org/problems/factorial/0) \
&#x20;

Following is implementation of factorial. \
&#x20;

* C++
* C
* Java
* Python3
* C#
* PHP
* Javascript

| `// C++ program to find factorial of given number#include <iostream>using` `namespace` `std;` `// function to find factorial of given numberunsigned int` `factorial(unsigned int` `n){    if` `(n == 0)        return` `1;    return` `n * factorial(n - 1);}` `// Driver codeint` `main(){    int` `num = 5;    cout << "Factorial of "         << num << " is "` `<< factorial(num) << endl;    return` `0;}` `// This code is contributed by Shivi_Aggarwal` |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Output:&#x20;

```
Factorial of 5 is 120
```

**Iterative Solution:** \
Factorial can also be calculated iteratively as recursion can be costly for large numbers. Here we have shown the iterative approach using both for and while loop. \
**Using For loop** \
&#x20;

* C++
* C
* Java
* Python3
* C#
* PHP
* Javascript

| `// C++ program for factorial of a number#include <iostream>using` `namespace` `std;` `// function to find factorial of given numberunsigned int` `factorial(unsigned int` `n){    int` `res = 1, i;    for` `(i = 2; i <= n; i++)        res *= i;    return` `res;}` `// Driver codeint` `main(){    int` `num = 5;    cout << "Factorial of "         << num << " is "         << factorial(num) << endl;    return` `0;}` `// This code is contributed by Shivi_Aggarwal` |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

**Output :** \
&#x20;

```
Factorial of 5 is 120
```

**Using While loop** \
&#x20;

* C
* C++
* Java
* Python3
* C#
* Javascript

| `// C program for factorial of a number#include <stdio.h>` `// function to find factorial of given numberunsigned int` `factorial(unsigned int` `n){     if(n == 0)          return` `1;    int` `i = n, fact = 1;    while` `(n / i != n) {        fact = fact * i;        i--;    }    return` `fact;}` `int` `main(){    int` `num = 5;    printf("Factorial of %d is %d", num, factorial(num));    return` `0;}` |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

**Output :** \
&#x20;

```
Factorial of 5 is 120
```

Time complexity of the above iterative solutions is O(n).\
**One line Solution (Using Ternary operator): **\
&#x20;

* C++
* C
* Java
* Python3
* C#
* PHP
* Javascript

| `// C++ program to find factorial of given number#include <iostream>using` `namespace` `std;` `int` `factorial(int` `n){    // single line to find factorial    return` `(n == 1 \|\| n == 0) ? 1 : n * factorial(n - 1);}` `// Driver Codeint` `main(){    int` `num = 5;    cout << "Factorial of "` `<< num << " is "<< factorial(num);    return` `0;}` `// This code is contributed by shivanisinghss2110` |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

**Output:**&#x20;

```
Factorial of 5 is 120
```
