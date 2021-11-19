# Bubble Sort



Bubble sort is the simplest sorting algorithm. It is based on comparison where each adjacent pair of element is compared and swapped if they are not in order. It works by repeatedly stepping through the list to be sorted, comparing two items at a time and swapping them if they are in the wrong order. The pass through the list is repeated until no swaps are needed, which means the list is sorted. This algorithm is not suitable for huge data sets. Average and worst case time complexity of this algorithm are of **Ο(n2) **where n is the number of items.

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

Suppose we have a list of array of 5 elements A\[5]={40,50,30,20,10}. We have to sort this array using bubble sort algorithm.

![Bubble-sort-example-MSA Technosoft](https://msatechnosoft.in/blog/wp-content/uploads/2018/09/Bubble-sort-example-MSA-Technosoft.png)

We observe in algorithm that Bubble Sort compares each pair of array element unless the whole array is completely sorted in an ascending order. After every iteration the highest values settles down at the end of the array. Hence, the next iteration need not include already sorted elements.

```
void bubbleSort(int arr[], int n)
{
    int i, j, temp;
    for(i = 0; i < n; i++)
    {
        for(j = 0; j < n-i-1; j++)
        {
            if( arr[j] > arr[j+1])
            {
// swap the elements
                temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
}
```
