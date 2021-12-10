# Stacks and Queues

[Source: Code Fellows - Stacks and Queues](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)

## Stacks

A **stack** is a data structure made up of `Nodes` where each node references the next node but not the previous.

### Stack Terms

* Push - the act of putting a node or item in a stack
* Pop - removing nodes or items from a stack. Attempting to pop an empty stack will raise an exception
* Top - The top of the stack
* Peek - Viewing teh value of the top node in the stack. Peeking an empty stack will raise an exception
* IsEmpty - returns true if a stack is empty.

### Stack concepts

FILO: First In Last Out - The first item pushed to a stack will the last item popped.

LIFO: Last In First Out - The last item pushed to a stack will be the first item popped.

Quite literally, imagine stacking values on top of each other like blocks. To remove them, you must start from the top and work your way down.

### Stack Complexity

* Push - O(1)
* Pop - O(1)
* Peek - O(1)
* IsEmpty - O(1)

## Queues

### Queue Terms

* Enqueue - Nodes or items added to a queue
* Dequeue - Nodes or items removed from a queue. Calling on an empty queue will raise an exception.
* Front - The first node in a queue
* Rear - The last node in a queue
* Peek - views the value of the front node in a queue. Calling on an empty queue will raise an exception.
* IsEmpty - returns true when queue is empty otherwise false.

### Queue Concepts

FIFO: First In First Out

LILO: Last In Last Out

Imagine a line for a roller coaster. The first person to get in line will be the first to board the coaster.

### Queue Complexity

* Enqueue - O(1)
* Dequeue - O(1)
* Peek - O(1)
* IsEmpty - O(1)
