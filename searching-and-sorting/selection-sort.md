# Selection Sort



Selection sort is an in-place comparison sort algorithm. In this algorithm, we repeatedly select the smallest remaining element and move it to the end of a growing sorted list. It is one of the simplest sorting algorithm. Selection sort is known for its simplicity. It has performance advantages over more complicated algorithms in certain situations.

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

In this algorithm we have to find the minimum value in the list first. Then, Swap it with the value in the first position. After that, Start from the second position and repeat the steps above for remainder of the list.

```
// function to look for smallest element in the given subarray
int indexOfMinimum(int arr[], int startIndex, int n)
{
    int minValue = arr[startIndex];
    int minIndex = startIndex;
    for(int i = minIndex + 1; i < n; i++) 
    {
        if(arr[i] < minValue)
        {
            minIndex = i;
            minValue = arr[i];
        }
    }
    return minIndex;
}

void selectionSort(int arr[], int n)
{
    for(int i = 0; i < n; i++)
    {
        int index = indexOfMinimum(arr, i, n);
        swap(arr, i, index);
    }
}
```
