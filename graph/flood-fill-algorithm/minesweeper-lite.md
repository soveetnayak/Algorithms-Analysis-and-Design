# Minesweeper Lite

## Replace all occurrences of 0 that are surrounded by 1 in a binary matrix

Given an `M × N` binary matrix, replace all occurrences of 0’s by 1’s, which are completely surrounded by 1’s from all sides (top, left, bottom, right, top-left, top-right, bottom-left, and bottom-right).

For example, consider the following matrix:

&#x20;\[  1  1  1  1  0  0  1  1  0  1  ]\
&#x20;\[  1  0  0  1  1  0  1  1  1  1  ]\
&#x20;\[  1  0  0  1  1  1  1  1  1  1  ]\
&#x20;\[  1  1  1  1  0  0  1  1  0  1  ]\
&#x20;\[  0  0  1  1  0  0  0  1  0  1  ]\
&#x20;\[  1  0  0  1  1  0  1  1  0  0  ]\
&#x20;\[  1  1  0  1  1  1  1  1  1  1  ]\
&#x20;\[  1  1  0  1  1  0  0  1  0  1  ]\
&#x20;\[  1  1  1  0  1  0  1  0  0  1  ]\
&#x20;\[  1  1  1  0  1  1  1  1  1  1  ]

The solution should convert it into the following matrix:

&#x20;\[  1  1  1  1  0  0  1  1  0  1  ]\
&#x20;\[  1  1  1  1  1  0  1  1  1  1  ]\
&#x20;\[  1  1  1  1  1  1  1  1  1  1  ]\
&#x20;\[  1  1  1  1  1  1  1  1  0  1  ]\
&#x20;\[  0  0  1  1  1  1  1  1  0  1  ]\
&#x20;\[  1  0  0  1  1  1  1  1  0  0  ]\
&#x20;\[  1  1  0  1  1  1  1  1  1  1  ]\
&#x20;\[  1  1  0  1  1  1  1  1  1  1  ]\
&#x20;\[  1  1  1  0  1  1  1  1  1  1  ]\
&#x20;\[  1  1  1  0  1  1  1  1  1  1  ]



We can use the [flood fill algorithm](https://www.techiedelight.com/flood-fill-algorithm/) to solve this problem. The idea is to consider all zeroes present on the matrix’s boundary one by one and start a [Depth–first search (DFS)](https://www.techiedelight.com/depth-first-search/) from them. The DFS procedure replaces all such connected zeroes by value `-1`.

After processing all connected zeroes present on the matrix boundary, traverse the matrix again, replace all remaining zeroes with `1` and replace all `-1`
