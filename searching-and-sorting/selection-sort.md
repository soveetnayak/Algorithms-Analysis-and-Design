# Selection Sort



Selection sort is a sorting method that uses in-place comparisons. We choose the smallest remaining element and move it to the end of a growing sorted list in this approach. It is one of the most basic sorting algorithms available. The selection sort is well-known for its ease of use. In some instances, it outperforms more sophisticated algorithms.

Time complexity is **Ο(n^2)**, where n is the number of items.

**Algorithm**

```
Step 1: Set MIN to location 0

Step 2: Search the minimum element in the list

Step 3: Swap with value at location MIN

Step 4: Increment MIN to point to next element

Step 5: Repeat until list is sorted
```

Example,

Let us assume an array A\[10]={45,20,40,05,15,25,50,35,30,10}. We have to sort this array using selection sort.

![Selection-sort-example-MSA Technosoft](https://msatechnosoft.in/blog/wp-content/uploads/2018/09/Selection-sort-example-MSA-Technosoft.png)

In this algorithm we have to find the minimum value in the list first. Then, Swap it with the value in the first position. After that, Start from the second position and repeat the steps above for the remainder of the list.
