# 0-1 Knapsack problem

In 0-1 Knapsack, items cannot be broken which means the thief should take the item as a whole or should leave it. This is reason behind calling it as 0-1 Knapsack.

Hence, in case of 0-1 Knapsack, the value of _**xi**_ can be either _**0**_ or _**1**_, where other constraints remain the same.

0-1 Knapsack cannot be solved by Greedy approach. Greedy approach does not ensure an optimal solution. In many instances, Greedy approach may give an optimal solution.

The following examples will establish our statement.

#### Example-1

Let us consider that the capacity of the knapsack is W = 25 and the items are as shown in the following table.

| Item   | A  | B  | C  | D  |
| ------ | -- | -- | -- | -- |
| Profit | 24 | 18 | 18 | 10 |
| Weight | 24 | 10 | 10 | 7  |

Without considering the profit per unit weight (_**pi/wi**_), if we apply Greedy approach to solve this problem, first item _**A**_ will be selected as it will contribute maximum profit among all the elements.

After selecting item _**A**_, no more item will be selected. Hence, for this given set of items total profit is _**24**_. Whereas, the optimal solution can be achieved by selecting items, _**B**_ and C, where the total profit is 18 + 18 = 36.

#### Example-2

Instead of selecting the items based on the overall benefit, in this example the items are selected based on ratio _pi/wi_. Let us consider that the capacity of the knapsack is _W_ = 60 and the items are as shown in the following table.

| Item   | A   | B   | C   |
| ------ | --- | --- | --- |
| Price  | 100 | 280 | 120 |
| Weight | 10  | 40  | 20  |
| Ratio  | 10  | 7   | 6   |

Using the Greedy approach, first item _**A**_ is selected. Then, the next item _**B**_ is chosen. Hence, the total profit is **100 + 280 = 380**. However, the optimal solution of this instance can be achieved by selecting items, _**B**_ and _**C**_, where the total profit is **280 + 120 = 400**.

Hence, it can be concluded that Greedy approach may not give an optimal solution.

To solve 0-1 Knapsack, Dynamic Programming approach is required.

#### Problem Statement

A thief is robbing a store and can carry a maximal weight of _**W**_ into his knapsack. There are _**n**_ items and weight of **ith** item is _**wi**_ and the profit of selecting this item is _**pi**_. What items should the thief take?

### Dynamic-Programming Approach

Let _**i**_ be the highest-numbered item in an optimal solution **S** for **W** dollars. Then _**S' = S - {i}**_ is an optimal solution for _**W - wi**_ dollars and the value to the solution _**S**_ is _**Vi**_ plus the value of the sub-problem.

We can express this fact in the following formula: define **c\[i, w]** to be the solution for items **1,2, … , i** and the maximum weight **w**.

The algorithm takes the following inputs

* The maximum weight **W**
* The number of items **n**
* The two sequences **v = \<v1, v2, …, vn>** and **w = \<w1, w2, …, wn>**

```
Dynamic-0-1-knapsack (v, w, n, W) 
for w = 0 to W do 
   c[0, w] = 0 
for i = 1 to n do 
   c[i, 0] = 0 
   for w = 1 to W do 
      if wi ≤ w then 
         if vi + c[i-1, w-wi] then 
            c[i, w] = vi + c[i-1, w-wi] 
         else c[i, w] = c[i-1, w] 
      else 
         c[i, w] = c[i-1, w] 
```

The set of items to take can be deduced from the table, starting at **c\[n, w]** and tracing backwards where the optimal values came from.

If _c\[i, w] = c\[i-1, w]_, then item _**i**_ is not part of the solution, and we continue tracing with **c\[i-1, w]**. Otherwise, item _**i**_ is part of the solution, and we continue tracing with **c\[i-1, w-W]**.
