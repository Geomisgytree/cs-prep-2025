# AVL, MST, Dijkstra, DP

This is a readme that includes notes of different algorithms.

## Selection Sort

Find the smallest unsorted element and add it to the end of the sorted list.

**In pseudocode**:
- Repeat until no unsorted elements remain:
  - Search the unsorted part of the data to find the smallest value
  - Swap the smallest found value with the first element of the unsorted part

**Complexity**:
- Worst-case scenario: Iterate over each of the n elements of the array (to find the smallest unsorted element) and we must repeat this process *n* times, since only one element gets sorted on each pass: $O(n)$
- Best-case scenario: Exactly the same. There's no way to guarantee the array is sorted until we go through this process for all elements: $\Omega(n)$

## Recursion
- Calls itself as part of the execution
  - An example: The factorial function (n!), fact(n). fact(5) = 5 * 4 * 3 * 2 * 1 = 5 * fact(4)
  - fact(n) = n * fact(n - 1)
  - Components: 1) base case: terminate the recursive process; 2) recursive case: where the recursion will actually occur
  - In general, but not always, recursive functions replace loops in non-recursive functions.

  ```java
  int fact(int n)
  {
    // base case
    if (n == 1)
        return 1;
    // recursive case
    else return n * fact(n-1);
  }

  


*Reference: CS50*