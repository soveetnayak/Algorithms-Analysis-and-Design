# Fractional Knapsack Problem

Given weights and values of n items, we need to put these items in a knapsack of capacity W to get the maximum total value in the knapsack.

```
Input: 
Items as (value, weight) pairs 
arr[] = {{60, 10}, {100, 20}, {120, 30}} 
Knapsack Capacity, W = 50; 

Output: 
Maximum possible value = 240 
by taking items of weight 10 and 20 kg and 2/3 fraction 
of 30 kg. Hence total price will be 60+100+(2/3)(120) = 240
```



In **Fractional Knapsack**, we can break items for maximizing the total value of knapsack. This problem in which we can break an item is also called the fractional knapsack problem.&#x20;

```
Input : 
Same as above

Output :
Maximum possible value = 240
By taking full items of 10 kg, 20 kg and 
2/3rd of last item of 30 kg
```

A **brute-force solution** would be to try all possible subsets with all different fractions but that will be too much time taking.&#x20;

An **efficient solution** is to use the Greedy approach.&#x20;

The basic idea of the greedy approach is to calculate the ratio value/weight for each item and sort the item on basis of this ratio.&#x20;

To do that, we sort the input in descending order of the ratio.

In the above example, the order will be {{60, 10}, {100, 20}, {120, 30}} .

Then take the item with the highest ratio and add them until we can’t add them anymore. Continue the process with the next element until the Knapsack weight is reached.&#x20;

This will always be the optimal solution to this problem.
