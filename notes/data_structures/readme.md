# Data structure

## arrays, linked_lists, stacks_queues, trees, graphs, dp

## Arrays

## Linked Lists
### Singly Linked Lists
- A linked list **node** is a special kind of struct with two members:
  - Data of same data type (int, char, float)
  - A pointer to another node of the same type
- A set of nodes together form a chain of elements that we can follow from beginning to end

```java
typedef struct sllist {
    VALUE val; // VALUE is an arbitrary data type
    struct sllist* next; // pointer to another node of the same type
}
sllnode; // create the name of the data type
```
- Operations:
  - Create one linked list
  ```java
  sllnode* create(VALUE val); // allocate space for sllnode, initialize val, next field, return a pointer to sllnode
  sllnode* new = create(6); // val: 6, next = NULL
  ```
  - Search through a linked list to find an element
  ```java
  bool find(sllnode* head, VALUE val); // only need to track the very first of the elements in the list
  bool exists = find(list, 6); // for a linked list: 2,3,5,6,8
  // No random access for the linked list, like it did in array
  ```
  - Insert new node into the linked list
  ```java
  sllnode* insert(sllnode* head, VALUE val); // pointer to the head of the list.
  // ## IMPORTANT: Insert the node at the beginning of the linked list!
  list = insert(list, 12);
  ```
  - Delete a single element from a linked list
  - Delete an entire linked list
  ```java
  void destroy(sllnode* head); // If you've reached a null pointer, stop. Delete the rest of the list
  ```

### Doubly Linked Lists
```java
typedef struct sllist {
    VALUE val; // VALUE is an arbitrary data type
    struct sllist* prev; // be able to move backwards
    struct sllist* next; // pointer to another node of the same type
}
sllnode; // create the name of the data type
```
- Insert a new node into the linked list
```java
dllnode* insert(dllnode* head, VALUE val); // Fix the prev pointer of the old head of the linked list
```
- Delete a single element from a linked list
```java
void delete(dllnode* target) // Fix the pointers of the surrounding nodes to "skip over" target
```

## Stacks
- Commonly implemented in one of the two ways: as an **array** or as a **linked list**
- Last in, first out (LIFO)
- Only two operations legally be performed:
  - Push: Add a new element to the top of the stack
  ```java
  void push(stack* s, VALUE data);
  ```
  - Pop: Remove the most recently-added element from the top of the stack
- Array-based implementation
```java
typedef struct _stack
{
    VALUE array[CAPACITY];
    int top; // the top of the elements
}
stack;
```

## Queues
- First in, first out (FIFO)
```java
typedef struct _queue
{
    VALUE array[CAPACITY];
    int front;
    int size;
}
queue;
```

## Hash Tables
- A data structure that stores unique keys to values ex. Integer, String. Each Key-value pair is known as an Entry
- Combine the **random access** ability of an array with the **dynamism** of a linked list
- Insertion, Deletion, Lookup can start to tend toward **constant time $\theta(1)$**
- Combine two things:
  - A **hash function** returning an nonnegative integer value called a *hash code*. **Hashing**: Takes a key and computes an integer. In the hashtable, we use the hash % capacity to calculate an index number.
    - key.hashCode() % capacity = index
  - An array capable of storing data of the type we wish to place into the data structure
  - The idea: Run data through the hash function, then store the data in the element of the array represented by the returned hash code
  - Runtime complexity: Best case O(1), Worst case O(n)
```java
  int y = hash("Paul");
  // y is now 6
  hashtable[y] = "Paul";

  // Implementation
  Hashtable<String, String> table = new Hashtable<>(10);
  // Add elements to the hash table
  table.put("100", "Spongebob");
  table.put("123", "Patrick");
  table.put("321", "Sandy");
  table.put("555", "Squidward");
  table.put("777", "Gary");

  // table.remove(777); // remove the 777 key
  // Print all the key-value pairs
  for(Integer key : table.keySet()){
    System.out.println(key.hashCode() % 10 + "\t" + key + "\t" + table.get()); // hashcode + key + value
    // IMPORTANT: Different data type will have different hash code formulas
  }

```
- **Collision**: A collision occurs when two pieces of data, when run through the hash function, yield the same code.
- **Linear probing**: If we have a collision, we try to place the data in the next consecutive element in the array until we find a vacancy.
- Resolve collisions: **Chaining** - What if each element of the array is a *pointer to the head of a linked list*, then multiple pieces of data can yield the same hash code and we will be able to store it all.



## Binary Trees
- Each node can have **at most** 2 children - left child + right child
- Leaf node: nodes that don't have children
- Max number of nodes at level i: $2^i$
- Max number of nodes in a binary tree with height h = 2^0 + 2^1 + ... + 2^h = 2^(h+1) - 1
- Height of perfect binary tree with n nodes = log_n^(n+1) - 1






*References: 《Grokking Algorithms》 by Aditya Y. Bhargava, CS50*