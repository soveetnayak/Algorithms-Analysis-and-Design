# Counting Sort



Counting sort is a sorting algorithm that sorts the elements of an array by counting the number of occurrences of each unique element in the array. The count is stored in an auxiliary array and the sorting is done by mapping the count as an index of the auxiliary array.

***

### Working of Counting Sort <a href="#working" id="working"></a>

1. Find out the maximum element (let it be `max`) from the given array.![Counting Sort steps](https://cdn.programiz.com/cdn/farfuture/\_iojSNQFxCvNdbdPPmMVCJZxGFTS0TOZRIt1E4Wte0Y/mtime:1582112622/sites/tutorial2program/files/Counting-sort-0\_0.png)Given array
2. Initialize an array of length `max+1` with all elements 0. This array is used for storing the count of the elements in the array.![Counting Sort Step](https://cdn.programiz.com/cdn/farfuture/bRDNfPQG8lie6m7EFXVqPj8w6RzkRhM34XNaAoG2dCs/mtime:1582112622/sites/tutorial2program/files/Counting-sort-1.png)Count array
3. Store the count of each element at their respective index in `count` array\
   \
   For example: if the count of element 3 is 2 then, 2 is stored in the 3rd position of count array. If element "5" is not present in the array, then 0 is stored in 5th position.![Counting Sort Step](https://cdn.programiz.com/cdn/farfuture/CIyC1Lkj5JFln\_hjy8U1acmUZ4JST\_\_v4bQBvPcnOkk/mtime:1582112622/sites/tutorial2program/files/Counting-sort-2.png)Count of each element stored
4. Store cumulative sum of the elements of the count array. It helps in placing the elements into the correct index of the sorted array.![Counting Sort Step](https://cdn.programiz.com/cdn/farfuture/6A5S6vY-KsapHcyBjGgLNrp-58NRdyGDeVXspSzUbwM/mtime:1582112622/sites/tutorial2program/files/Counting-sort-3.png)Cumulative count
5. Find the index of each element of the original array in the count array. This gives the cumulative count. Place the element at the index calculated as shown in figure below.![Counting Sort Steps](https://cdn.programiz.com/cdn/farfuture/tcfjQdeYwL\_jETOCPZxNjIXbysRrb7MaG6PwO2MzHnM/mtime:1582112622/sites/tutorial2program/files/Counting-sort-4\_1.png)Counting sort
6. After placing each element at its correct position, decrease its count by one.

***

### Counting Sort Algorithm <a href="#algorithm" id="algorithm"></a>

```
countingSort(array, size)
  max <- find largest element in array
  initialize count array with all zeros
  for j <- 0 to size
    find the total count of each unique element and 
    store the count at jth index in count array
  for i <- 1 to max
    find the cumulative sum and store it in count array itself
  for j <- size down to 1
    restore the elements to array
    decrease count of each element restored by 1
```

{% hint style="warning" %}
Given an integer array with many duplicated elements, write an algorithm to efficiently sort it in linear time, where the order of equal elements doesn’t matter.
{% endhint %}

For example,

**Input:** { 4, 2, 40, 10, 10, 1, 4, 2, 1, 10, 40 }

A simple solution would be to use efficient sorting algorithms like Merge Sort, Quicksort, Heapsort, etc., that can solve this problem in O(n.log(n)) time, but those will not take advantage of the fact that there are many duplicated values in the array.

&#x20;\
A better approach is to use a counting sort. This will bring down the time complexity to O(n + k), where `n` is the size of the input and `k` is the input range.

**Output:** { 1, 1, 2, 2, 4, 4, 10, 10, 10, 40, 40 }
