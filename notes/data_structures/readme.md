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

## Trees and Binary-Search Trees





*References: 《Grokking Algorithms》 by Aditya Y. Bhargava, CS50*