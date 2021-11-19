# Binary Search



Binary Search Algorithm is fast according to run time complexity. This algorithm works on the basis of divide and conquer rule. In this algorithm we have to sort the data collection in ascending order first then search for the targeted item by comparing the middle most item of the collection. If match found, the index of item is returned. If the middle item is greater than the targeted item, the item is searched in the sub-array to the left of the middle item. Otherwise, the item is searched for in the sub-array to the right of the middle item. This process continues on the sub-array as well until the size of the sub array reduces to zero.

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

Let us take an example of an array A\[16]={1,2,3,4,6,7,8,10,12,13,15,16,18,19,20,22}. The array is sorted and contains 16 items. We are looking for item 19 in this list.

Here, we have

A\[16]={1,2,3,4,6,7,8,10,12,13,15,16,18,19,20,22}

X=19

Let us first divide it into two smaller arrays of 8 items each. The first 8 items in a sub array and another 8 in another sub array. A1={1,2,3,4,6,7,8,10} and A2={12,13,15,16,18,19,20,22}

As 10 and 12 are the middle items of this ordered array, we know 19 is greater than the middle numbers that means we don’t require to look for the targeted item in first sub array. Let us search in the second subarray A2={12,13,15,16,18,19,20,22}

In the second array we have 8 items. Let’s divide them into two equal arrays and check the middle items. Here the middle items are 16 and 18. As 19 is greater than both of them, we don’t need to look in the first four items of this subarray. A21={12,13,15,15} and A22={18,19,20,22}

Let us look in the last four items sub array A22={18,19,20,22}. Let us again divide it to subarrays A221={18,19) and A222={20,22}. Here the middle items are 19 and 20. Hence, we found the target item 19 in first subarray.

Time complexity of Binary search algorithm is **O(logn) or O(n)**.

```
int binarySearch(int values[], int len, int target)
{
    int max = (len - 1);
    int min = 0;
    int guess; // index of middle elements
    int step = 0; // to find out in how many steps we completed the search
    while(max >= min)
    {
        guess = (max + min) / 2;
        // we made the first guess, incrementing step by 1
        step++;
        if(values[guess] == target)
        {
            printf("Number of steps required for search: %d \n", step);
            return guess;
        }
        else if(values[guess] > target)
        {
        // target would be in the left half
        max = (guess - 1);
        }
        else
        {
        // target would be in the right half
        min = (guess + 1);
        }
    }
    // Element not found
    return -1;
}
```
