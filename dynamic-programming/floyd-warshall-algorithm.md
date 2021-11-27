# Floyd-Warshall Algorithm

Floyd-Warshall Algorithm is an algorithm for finding the shortest path between all the pairs of vertices in a weighted graph. This algorithm works for both the directed and undirected weighted graphs. But, it does not work for the graphs with negative cycles (where the sum of the edges in a cycle is negative).

A weighted graph is a graph in which each edge has a numerical value associated with it.

Floyd-Warhshall algorithm is also called as Floyd's algorithm, Roy-Floyd algorithm, Roy-Warshall algorithm, or WFI algorithm.

This algorithm follows the dynamic programming approach to find the shortest paths.&#x20;

***

### How Floyd-Warshall Algorithm Works? <a href="working" id="working"></a>

Let the given graph be:

![graph](https://cdn.programiz.com/sites/tutorial2program/files/fw-Graph.png)Initial graph

Follow the steps below to find the shortest path between all the pairs of vertices.

1. Create a matrix `A0` of dimension `n*n` where n is the number of vertices. The row and the column are indexed as i and j respectively. i and j are the vertices of the graph.\
   \
   Each cell A\[i]\[j] is filled with the distance from the `ith` vertex to the `jth` vertex. If there is no path from `ith` vertex to `jth` vertex, the cell is left as infinity.![matrix floyd warshall algorithm](https://cdn.programiz.com/sites/tutorial2program/files/fw-Matrix-1.png)Fill each cell with the distance between ith and jth vertex
2. Now, create a matrix `A1` using matrix `A0`. The elements in the first column and the first row are left as they are. The remaining cells are filled in the following way.\
   \
   Let k be the intermediate vertex in the shortest path from source to destination. In this step, k is the first vertex. `A[i][j]` is filled with `(A[i][k] + A[k][j]) if (A[i][j] > A[i][k] + A[k][j])`.\
   \
   That is, if the direct distance from the source to the destination is greater than the path through the vertex k, then the cell is filled with `A[i][k] + A[k][j]`.\
   \
   In this step, k is vertex 1. We calculate the distance from source vertex to destination vertex through this vertex k.![matrix floyd warshall algorithm](https://cdn.programiz.com/sites/tutorial2program/files/fw-Matrix-2.png)Calculate the distance from the source vertex to destination vertex through this vertex k\
   For example: For `A1[2, 4]`, the direct distance from vertex 2 to 4 is 4 and the sum of the distance from vertex 2 to 4 through vertex (ie. from vertex 2 to 1 and from vertex 1 to 4) is 7. Since `4 < 7`, `A0[2, 4]` is filled with 4.
3. Similarly, `A2` is created using `A1`. The elements in the second column and the second row are left as they are.\
   \
   In this step, k is the second vertex (i.e. vertex 2). The remaining steps are the same as in **step 2**.![matrix floyd warshall algorithm](https://cdn.programiz.com/sites/tutorial2program/files/fw-Matrix-3.png)Calculate the distance from the source vertex to destination vertex through this vertex 2
4. Similarly, `A3` and `A4` is also created.![matrix floyd warshall algorithm](https://cdn.programiz.com/sites/tutorial2program/files/fw-Matrix-4.png)Calculate the distance from the source vertex to destination vertex through this vertex 3 ![matrix floyd warshall algorithm](https://cdn.programiz.com/sites/tutorial2program/files/fw-Matrix-5.png)Calculate the distance from the source vertex to destination vertex through this vertex 4
5. `A4` gives the shortest path between each pair of vertices.

***

### Floyd-Warshall Algorithm <a href="algortihm" id="algortihm"></a>

```
n = no of vertices
A = matrix of dimension n*n
for k = 1 to n
    for i = 1 to n
        for j = 1 to n
            Ak[i, j] = min (Ak-1[i, j], Ak-1[i, k] + Ak-1[k, j])
return A
```
