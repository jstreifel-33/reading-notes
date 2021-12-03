# Big O & Linked List

## Big O Revisited

[Source: Code Fellows - Big O: Analysis of Algorithm Efficiency](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/big_oh.html)

Big O is used to described the efficiency of an algorithm or function, and is based on 2 factors: **Time Efficiency** and **Space Efficiency**.

When evaluating Big O there are 4 key areas to consider:

1. Input Size
2. Units of Measurement
3. Orders of Growth
4. Best Case, Worst Case, and Average Case

### Input Size

The size of parameters read by the algorithm. Referred to using `n`.

The higher the input size, the more likely Run Time and Memory Space will increase.

### Units of Measurement

When evaluating Time and Space complexity, we'll need a way to measure these two things.

* **Time Complexity**
  * Time in **milliseconds** from start to finish
  * Number of **operations** executed
  * Number of **basic operations** executed
* **Space Complexity**
  * Space needed for the **code itself**
  * Space needed to hold the **input** data
  * Space needed to hold the **output** data
  * **Working space** during calculation

### Orders of Growth

Order of Growth refers to the rate at which complexity grows as n increases.

* O(n) - linear
* O(lgn) - logarithmic
* O(nlgn) - linearithmic
* n^2 - quadratic
* n^3 - cubic
* 2^n - exponential
* n! - factorial

### Worst Case, Best Case, Average Case

`Big O` notation describes the Worst Case for an algorithm

`Big Omega` notation describes the Best Case for an algorithm

`Big Theta` notation describes the Average Case for an algorithm

## Linked Lists

[Source: Code Fellows - Linked Lists](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)

A Linked List is a sequence of *Nodes* that are connected to each other. Each Node refers to the next Node in the link.

Terms to know:

* Linked List - Data structure composed of nodes.
* Singly - in singly linked lists each node points to the **next** node.
* Doubly - in doubly linked lists, nodes refer to the **next** and **previous** nodes
* Node - the individual items and links that live in a linked list.
* Next - Each node contains a `next` property, containing a reference to the next node.
* Head - Reference of type `Node` to the first node in a linked list.
* Current - Reference of type `Node` to the currently looked at node.

**Traversal** can be accomplished with a while loop.

## More on Linked Lists

Source:

[What's a Linked List, Anyway Pt. 1](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)

[What's a Linked List, Anyway Pt. 2](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)

Linked Lists are called **Non-linear data structures**. The data inside of them is traversed non-sequentially.

Arrays and other linear data structures take up contiguous blocks of memory. Cases like this are referred to as **static**.

Linked lists and other non-linear data structures don't require contiguous memory. Their bytes can be anywhere. Cases like this are referred to as **dynamic**

The nodes of a linked list are only aware of their immediate neighbors.

Inserting an element at the beginning of linked list has O(1) complexity. It is constant.

inserting an element at the end of a linked list has O(n) complexity. It is linear.

Rule of thumb from reading:

> a linked list is usually efficient when it comes to adding and removing most elements, but can be very slow to search and find a single element.

**Lists** are helpful if you know the size of the list, you need random access to elements, or want to iterate quickly. (Randomly accessed)

**Linked Lists** are helpful if you don't know the size of the list, and mostly want to add/remove things quickly. (Not randomly accessed)