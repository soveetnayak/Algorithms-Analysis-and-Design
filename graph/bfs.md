# BFS



### BFS algorithm <a href="algorithm" id="algorithm"></a>

A standard BFS implementation puts each vertex of the graph into one of two categories:

1. Visited
2. Not Visited

The purpose of the algorithm is to mark each vertex as visited while avoiding cycles.

The algorithm works as follows:

1. Start by putting any one of the graph's vertices at the back of a queue.
2. Take the front item of the queue and add it to the visited list.
3. Create a list of that vertex's adjacent nodes. Add the ones which aren't in the visited list to the back of the queue.
4. Keep repeating steps 2 and 3 until the queue is empty.

The graph might have two different disconnected parts so to make sure that we cover every vertex, we can also run the BFS algorithm on every node

***

### BFS example <a href="example" id="example"></a>

Let's see how the Breadth First Search algorithm works with an example. We use an undirected graph with 5 vertices.

![undirected graph with 5 vertices](https://cdn.programiz.com/sites/tutorial2program/files/graph-bfs-step-0.png)Undirected graph with 5 vertices

We start from vertex 0, the BFS algorithm starts by putting it in the Visited list and putting all its adjacent vertices in the stack.

![visit start vertex and add its adjacent vertices to queue](https://cdn.programiz.com/sites/tutorial2program/files/graph-bfs-step-1.png)Visit start vertex and add its adjacent vertices to queue

Next, we visit the element at the front of queue i.e. 1 and go to its adjacent nodes. Since 0 has already been visited, we visit 2 instead.

![visit the first neighbour of start node 0, which is 1](https://cdn.programiz.com/sites/tutorial2program/files/graph-bfs-step-2\_2.png)Visit the first neighbour of start node 0, which is 1

Vertex 2 has an unvisited adjacent vertex in 4, so we add that to the back of the queue and visit 3, which is at the front of the queue.

![visit 2 which was added to queue earlier to add its neighbours](https://cdn.programiz.com/sites/tutorial2program/files/graph-bfs-step-3.png)Visit 2 which was added to queue earlier to add its neighbours![visit](https://cdn.programiz.com/sites/tutorial2program/files/graph-bfs-step-4.png)4 remains in the queue

Only 4 remains in the queue since the only adjacent node of 3 i.e. 0 is already visited. We visit it.

![visit last remaining item in stack to check if it has unvisited neighbours](https://cdn.programiz.com/sites/tutorial2program/files/graph-bfs-step-5.png)Visit last remaining item in the stack to check if it has unvisited neighbors

Since the queue is empty, we have completed the Breadth First Traversal of the graph.

***

### BFS pseudocode <a href="pseudocode" id="pseudocode"></a>

```
create a queue Q 
mark v as visited and put v into Q 
while Q is non-empty 
    remove the head u of Q 
    mark and enqueue all (unvisited) neighbours of u
```

### BFS Algorithm Complexity <a href="complexity" id="complexity"></a>

The time complexity of the BFS algorithm is represented in the form of `O(V + E)`, where V is the number of nodes and E is the number of edges.

The space complexity of the algorithm is `O(V)`.
