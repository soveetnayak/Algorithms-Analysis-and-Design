# Linear Search



Linear Search Algorithm is the simplest search algorithm. In this search algorithm, a sequential search is made over all the items one by one to search for the targeted item. Each item is checked in sequence until the match is found. If the match is found, a particular item is returned otherwise the search continues till the end.

**Algorithm**

```
LinearSearch ( Array A, Value x)

Step 1: Set i to 1

Step 2: if i > n then go to step 7

Step 3: if A[i] = x then go to step 6

Step 4: Set i to i + 1

Step 5: Go to Step 2

Step 6: Print Element x Found at index i and go to step 8

Step 7: Print element not found

Step 8: Exit
```

**Linear Search Example**

{% hint style="warning" %}
Let us take an example of an array A\[7]={5,2,1,6,3,7,8}. Array A has 7 items. Let us assume we are looking for 7 in the array. Targeted item=7.
{% endhint %}



Here, we have

A\[7]={5,2,1,6,3,7,8}

X=7

At first, When i=0 (A\[0]=5; X=7) not matched

i++ now, i=1 (A\[1]=2; X=7) not matched

i++ now, i=2(A\[2])=1; X=7)not matched

…

….

i++ when, i=5(A\[5]=7; X=7) Match Found

Hence, Element X=7 found at index 5.

Linear search is rarely used practically. The time complexity of above algorithm is **O(n)**.

```
int linearSearch(int values[], int target, int n)
{
    for(int i = 0; i < n; i++)
    {
        if (values[i] == target)
        {
            return i;
        }
    }
    return -1;
}

```



{% hint style="warning" %}
You are given $$N$$N $$(3≤N≤5000)$$(3≤N≤5000) integer points on the coordinate plane. Find the square of the maximum Euclidean distance (aka length of the straight line) between any two of the points.
{% endhint %}

We can iterate through every pair of points and find the square of the distance between them, by squaring the formula for Euclidean distance:

$$
distance[(x1,y1),(x2,y2)]2=(x2−x1)2+(y2−y1)2.\text{distance}[(x_1,y_1),(x_2,y_2)]^2 = (x_2-x_1)^2 + (y_2-y_1)^2.distance[(x1​,y1​),(x2​,y2​)]2=(x2​−x1​)2+(y2​−y1​)2.
$$

Maintain the current maximum square distance in `max_square`.

* Since we're iterating through all pairs of points, we start the j loop from $$j=i+1$$ so that point i  and point j are never the same point. Furthermore, it makes it so that each pair is only counted once. In this problem, it doesn't matter whether we double-count pairs or whether we allow i and j to be the same point, but in other problems where we're counting something rather than looking at the maximum, it's important to be careful that we don't overcount.
