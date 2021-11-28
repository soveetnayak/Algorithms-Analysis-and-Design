# Flood Fill Algorithm

## Flood Fill Algorithm

Flood fill (also known as seed fill) is an algorithm that determines the area connected to a given node in a multi-dimensional array.

It is used in the “bucket” fill tool of a paint program to fill connected, similarly colored areas with a different color and in games such as Go and Minesweeper for determining which pieces are cleared. When applied on an image to fill a particular bounded area with color, it is also known as boundary fill.

&#x20;\
The flood fill algorithm takes three parameters: a start node, a target color, and a replacement color.

Consider the following matrix to the left – if the start node is `(3, 9)`, target color is **“BLACK”** and replacement color is **“GREY”**, the algorithm looks for all nodes in the matrix that are connected to the start node by a path of the target color and changes them to the replacement color.

&#x20;\
![Flood Fill Algorithm](https://www.techiedelight.com/wp-content/uploads/Flood-Fill.png)

_Note that each cell of the matrix represents one pixel._

### Approach 1: (Using BFS) <a href="bfs" id="bfs"></a>

A queue-based implementation using Breadth–first search (BFS) is shown below in pseudocode.

**BFS (starting-pixel, replacement-color):**

1. Create an empty queue.
2. Enqueue starting pixel and mark it as processed.
3. Loop till queue is empty
   1. Dequeue the front node and process it.
   2. Replace the color of the current pixel (popped node) with that of the replacement.
   3. Process all eight adjacent pixels of the current pixel and enqueue each valid pixel that has the same color as that of the current pixel.

### Approach 2: (Using DFS) <a href="dfs" id="dfs"></a>

We can use Depth–first search (DFS) to solve this problem. The idea is to start from the source node in the matrix, replace its color with the replacement color and recursively explore all its valid eight adjacent pixels, and replace their color. Note that we don’t need a visited array here as we are replacing the color of every processed node, and it won’t be considered again next time as it will have a different color.



\


\
