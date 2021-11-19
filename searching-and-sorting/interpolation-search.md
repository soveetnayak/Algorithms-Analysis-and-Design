# Interpolation Search

Interpolation Search Algorithm is an improvement of Binary Search. It works on the probing position of the required item. It works properly in sorted and equally distributed data lists.

**Algorithm**

```
Step 1: Start searching data from middle of the list.

Step 2: If it is a match, return the index of the item, and exit.

Step 3: If it is not a match, probe position.

Step 4: Divide the list using probing formula and find the new middle.

Step 5: If data is greater than middle, search in higher sub-list.

Step 6: If data is smaller than middle, search in lower sub-list.

Step 7: Repeat until match.
```

To divide the list into two sub lists, we use **mid = Lo + ((Hi – Lo) / (A\[Hi] – A\[Lo])) \* (X – A\[Lo])**

Where,

A = list

Lo = Lowest index of the list

Hi = Highest index of the list

A\[n] = Value stored at index n in the list

Runtime complexity of interpolation search algorithm is **Ο(log (log n))**.
