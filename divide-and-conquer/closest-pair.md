# Closest Pair

We are given an array of n points in the plane, and the problem is to find out the closest pair of points in the array. This problem arises in a number of applications. For example, in air-traffic control, you may want to monitor planes that come too close together, since this may indicate a possible collision. Recall the following formula for distance between two points p and q.

\
![\left \\|pq \right \\| = \sqrt{(p\_{x}-q\_{x})^{2}+ (p\_{y}-q\_{y})^{2}}](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-7d6624c81679b228b67c3252fca3dbb9\_l3.svg)

\
The Brute force solution is O(n^2), compute the distance between each pair and return the smallest.&#x20;

We can calculate the smallest distance in O(n(Logn)^2) time using Divide and Conquer strategy.

**Algorithm** \
Following are the detailed steps of a O(n (Logn)^2) algorithm.&#x20;

\
_Input:_ An array of n points _P\[]_ \


_Output:_ The smallest distance between two points in the given array.\
As a pre-processing step, the input array is sorted according to x coordinates.\


**1)** Find the middle point in the sorted array, we can take _P\[n/2]_ as middle point. \


**2)** Divide the given array in two halves. The first subarray contains points from P\[0] to P\[n/2]. The second subarray contains points from P\[n/2+1] to P\[n-1].\


**3)** Recursively find the smallest distances in both subarrays. Let the distances be dl and dr. Find the minimum of dl and dr. Let the minimum be d.\


![](https://media.geeksforgeeks.org/wp-content/uploads/mindis.png)

\
\


**4)** From the above 3 steps, we have an upper bound d of minimum distance. Now we need to consider the pairs such that one point in pair is from the left half and the other is from the right half. Consider the vertical line passing through P\[n/2] and find all points whose x coordinate is closer than d to the middle vertical line. Build an array strip\[] of all such points.&#x20;

![](https://media.geeksforgeeks.org/wp-content/uploads/closepair.png)

**5)** Sort the array strip\[] according to y coordinates. This step is O(nLogn).

\
**6)** Find the smallest distance in strip\[]. From the first look, it seems to be a O(n^2) step, but it is actually O(n). It can be proved geometrically that for every point in the strip, we only need to check at most 7 points after it (note that strip is sorted according to Y coordinate).&#x20;

\
**7)** Finally return the minimum of d and distance calculated in the above step (step 6)
