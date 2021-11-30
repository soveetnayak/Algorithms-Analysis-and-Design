# Binary Search



According to run time complexity, the Binary Search Algorithm is quick. This algorithm is based on the [divide and conquer](broken-reference) strategy.&#x20;

In this procedure, we must first sort the data collection in ascending order before searching for the desired item by comparing the collection's middle item. If there is a match, the item's index is returned. The item is searched in the sub-array to the left of the middle item if the middle item is greater than the targeted item. Otherwise, look for the item in the sub-array to the right of the centre item. This method is repeated on the sub-array until the sub-size array's is reduced to zero.

**Algorithm**

```
Step 1: Data list must be ordered list in ascending order.

Step 2: Probe middle of list

Step 3: If target equals list[mid], FOUND.

Step 4: If target < list[mid], discard 1/2 of list between list[mid] and list[last].

Step 5: If target > list[mid], discard 1/2 of list between list[first] and list[mid].

Step 6: Continue searching the shortened list until either the target is found, or there are no elements to probe.
```

**Binary Search Example**

Let us take an example of an array **A\[16]={1,2,3,4,6,7,8,10,12,13,15,16,18,19,20,22}**.&#x20;

The array is sorted and contains 16 items. We are looking for item 19 in this list.

Here, we have

A\[16]={1,2,3,4,6,7,8,10,12,13,15,16,18,19,20,22}

X=19

* Let us first divide it into two smaller arrays of 8 items each. The first 8 items in a sub array and another 8 in another sub array. A1={1,2,3,4,6,7,8,10} and A2={12,13,15,16,18,19,20,22}
* As 10 and 12 are the middle items of this ordered array, we know 19 is greater than the middle numbers that means we don’t require to look for the targeted item in first sub array. Let us search in the second subarray A2={12,13,15,16,18,19,20,22}
* In the second array we have 8 items. Let’s divide them into two equal arrays and check the middle items. Here the middle items are 16 and 18. As 19 is greater than both of them, we don’t need to look in the first four items of this subarray. A21={12,13,15,15} and A22={18,19,20,22}
* Let us look in the last four items sub array A22={18,19,20,22}. Let us again divide it to subarrays A221={18,19) and A222={20,22}. Here the middle items are 19 and 20. Hence, we found the target item 19 in first subarray.

Time complexity of Binary search algorithm is **O(logn)**.
