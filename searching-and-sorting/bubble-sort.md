# Bubble Sort



The simplest sorting algorithm is bubble sort. It works by comparing each adjacent pair of elements and swapping them if they are out of order. It works by walking through the list to be sorted many times, comparing two items at a time and exchanging them if they are out of order. The process is continued until no swaps are required, indicating that the list is sorted.

Time complexity of this algorithm are of **Ο(n^2)** where n is the number of items.

**Algorithm**

```
for i=N-1 to 2 {

set swap flag to false

for j=1 to i {

if list[j-1] > list[j]

swap list[j-1] and list[j]

set swap flag to true

}

if swap flag is false, break. The list is sorted.

}
```

\[NOTE: In each pass, the largest item “bubbles” down the list until it settles in its final position. This is where bubble sort gets its name.]

Example,

Suppose we have a list of array of 5 elements **A\[5]={40,50,30,20,10}**. We have to sort this array using bubble sort algorithm.

![Bubble-sort-example-MSA Technosoft](https://msatechnosoft.in/blog/wp-content/uploads/2018/09/Bubble-sort-example-MSA-Technosoft.png)

We observe in algorithm that Bubble Sort compares each pair of array element unless the whole array is completely sorted in an ascending order. After every iteration the highest values settles down at the end of the array. Hence, the next iteration need not include already sorted elements.
