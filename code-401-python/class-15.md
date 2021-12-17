# Data Structure: Trees

[Source: Code Fellows - Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)

Three types of trees will be covered here: binary trees, binary search trees, and k-ary trees.

## Terms to Know

* Node - component which may contain a value and references to other nodes
* Root - the node at the beginning of a tree
* K - maximum children a node may have in a k-ary tree
* Left - reference to one child in binary tree
* Right - reference to other child in binary tree
* Edge - the link between a child and parent
* Leaf - a node with no children
* Height - number of edges from root to furthest leaf.

## Traversal

There are two categories of traversal for trees: **depth first** and **breadth first**.

### Depth First Traversal

Prioritizes going through the depth of a tree first. Most commonly performed with recursion, which utilizes the function call stack. There are 3 methods for this:

* Pre-order `root >> left >> right`
* In-order `left >> root >> right`
* Post-order `left >> right >> root`

The most significant difference between these 3 methods is **when the root is looked at**.

### Breadth First Traversal

Iterates through tree level-by-level. Traditionally accomplished using a Queue.

```latex
pseudocode from reading:

ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while breadth.peek()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)
```

## K-ary Trees

Nodes can have more than two children, in which case a tree is referred to as a k-ary tree.

K-ary trees are traversed using a similar approach to breadth first traversal of binary trees.

```latex
From reading source:

ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while breadth.peek()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    for child in front.children
        breadth.enqueue(child)
```

## Binary Search Trees

Tree with a little more organization. Values greater than a node are on the left, while the opposite values are on the right.

Searches through a binary search tree are best accomplished using a while loop to iterate.
