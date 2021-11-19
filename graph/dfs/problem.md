# Problem

## Generate a list of possible words from a character matrix

Given an `M × N` boggle board, find a list of all possible words that can be formed by a sequence of adjacent characters on the board.

We are allowed to search a word in all eight possible directions, i.e., North, West, South, East, North-East, North-West, South-East, South-West, but a word should not have multiple instances of the same cell.

&#x20;\
Consider the following the traditional `4 × 4` boggle board. If the input dictionary is `[START, NOTE, SAND, STONED]`, the valid words are `[NOTE, SAND, STONED]`.

![Boggle Board](https://www.techiedelight.com/wp-content/uploads/boggle-board.png)

> [Practice this problem](https://techiedelight.com/practice/?problem=BoggleSearch)

&#x20;\
We can use [Depth–first search (DFS)](https://www.techiedelight.com/depth-first-search/) to solve this problem. The idea is to start from each character in the matrix and explore all eight paths possible and recursively check if they lead to a solution or not. To make sure that a word doesn’t have multiple instances of the same cell, keep track of cells involved in the current path in the matrix, and before exploring any cell, ignore the cell if it is already covered in the current path.

To find all possible movements from a cell, we can use an array to store the relative position of movement from any cell. For example, if the current cell is `(x, y)`, we can move to `(x + row[k], y + col[k])` for `0 <= k <=7` using the following array:

int row\[] = { -1, -1, -1, 0, 0, 1, 1, 1 }\
int col\[] = { -1, 0, 1, -1, 1, -1, 0, 1 }

So, from position `(x, y)`, we can move to:

(x – 1, y – 1)\
(x – 1, y)\
(x – 1, y + 1)\
(x, y – 1)\
(x, y + 1)\
(x + 1, y – 1)\
(x + 1, y)\
(x + 1, y + 1)
