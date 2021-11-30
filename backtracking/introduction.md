# Introduction

A backtracking algorithm is a problem-solving algorithm that uses a **brute force approach** for finding the desired output.

The brute force strategy tests all alternative solutions before selecting the desired/best one. Backtracking implies that if the present answer isn't working, you should go back and try something else.

&#x20;As a result, recursion is employed in this method. When there are several solutions to a problem, this method is utilised to solve it.

### State Space Tree <a href="#tree" id="tree"></a>

A space state tree is a tree representing all the possible states (solution or nonsolution) of the problem from the root as an initial state to the leaf as a terminal state.

![State Space Tree](https://cdn.programiz.com/sites/tutorial2program/files/ba-state-space-tree.png)State Space Tree

***

### Backtracking Algorithm <a href="#algorithm" id="algorithm"></a>

```
Backtrack(x)
    if x is not a solution
        return false
    if x is a new solution
        add to list of solutions
    backtrack(expand x)
```

***

### Example Backtracking Approach <a href="#example" id="example"></a>

Problem: You want to find all the possible ways of arranging 2 boys and 1 girl on 3 benches. Constraint: Girl should not be on the middle bench.

Solution: There are a total of 3! = 6 possibilities. We will try all the possibilities and get the possible solutions. We recursively try all the possibilities.

All the possibilities are:

![All the possibilities](https://cdn.programiz.com/sites/tutorial2program/files/ba-possibilities.png)All the possibilities

The following state space tree shows the possible solutions.

![State state tree](https://cdn.programiz.com/sites/tutorial2program/files/ba-state-state-tree-example.png)State tree with all the solutions

***

\
