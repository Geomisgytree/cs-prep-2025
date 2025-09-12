# Algorithms
This is a readme that includes notes of different algorithms.

# Table of Contents
- [Selection Sort](#selection-sort)
- [Recursion](#recursion)

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


## AVL (Self-Balancing BST)
Rotations are performed only on three nodes.
AVL tree is a height-balanced BST (Binary Search Tree).
- Calculate **balance factor** for each node: height of left subtree - height of right subtree = {-1, 0, 1}
- LL Rotation, LR Rotation, RR Rotation, RL Rotation
- If multiple nodes are imbalanced, from the **latest inserted node**, trace back to the **first imbalanced node**. That node will be where we should perform rotation.
- Complexity: O(log(n))

@youtube 10.1 AVL Tree - Insertion and Rotations by Abdul Bari [link](https://www.youtube.com/watch?v=jDM6_TnYIqE)

## MST (Minimum Spanning Tree)
- Graph is represented by: G = (V,E), V = {1,2,3,4,5,6}, E = {(1,2), (2,3), (3,4), ...}, n = 6 (number of vertices)
- **Spanning tree**: subgraph of a graph - take all vertices but a (n-1 = 5) edges
  - 6C5 ways (from 6 edges, choose 5 edges) = 6 different spanning trees
  - Generalization: $$C^{\text{Number of edges}}_{\text{Number of edges - 1}} - \text{Number of cycles}$$
  - **Minimum Spanning Tree**: Cost of the spanning tree will be varying. Find the minimum cost spanning tree: Using greedy method: 1) Prim's; 2) Kruskals
    - *Prim's Algorithm:* Select a minimum cost edge first, then, always select minimum cost edges that will connect to the previous edge.
    - *Kruskals Method*: Find the minimum cost edge first, and then select all the edges that have the minimum costs. Don't include the edge if it forms a cycle. Complexity: $O(n^2)$

References:
1. @youtube Prims and Kruskals Algorithms - Greedy Method [link](https://www.youtube.com/watch?v=4ZlRH0eK-qQ)
2. @youtube Graphs - Data Structures in 5 Minutes by Dickson Tsai [link](https://www.youtube.com/watch?v=vfCo5A4HGKc)
3. @CLRS Ch23 [link](https://www.cs.mcgill.ca/~akroit/math/compsci/Cormen%20Introduction%20to%20Algorithms.pdf)

## Dijkstra Algorithm

CLRS ch24

## Dynamic Programming (DP)

CLRS ch15


*Reference:*
- Introduction to Algorithms, third edition