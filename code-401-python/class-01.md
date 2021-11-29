# Pain, Suffering, and Big O

## Pain and Suffering

[Source: Codefellows Pain vs. Suffering](https://codefellows.github.io/code-401-python-guide/curriculum/class-01/notes/pain_suffering)

The course that we are about to embark on is designed to be painful.

This is not to be confused with suffering. **Suffering is pain without purpose.**

The pain we'll experience is the pain of growth, and something to be pushed past. It is not permanent and has a purpose in moments of pain.

The pain is expected, but there are ways to soften it. We should ask questions to those with knowledge, research things we don't understand, and develop a system or tools we can fall back on to make the pain of growth manageable.

We must not fear the pain of growth, but rather embrace it and leverage it to produce stronger versions of ourselves.

## Getting started with Big O

[Source: A beginner's guide to Big O Notation - Rob Bell](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation)

**Big O notation** describes the performance or complexity of an algorithm. It is used to describe the worst-case execution time or memory space used by a program.

When describing performance, it is important to remember that Big O assumes *worst-case performance*. This means that things like looping through data to find a match are assumed to take the **maximum number of iterations possible**.

* **O(1)** - an algorithm that will always execute in the same amount of time or space, regardless of input data.
* **O(N)** - an algorithm whose performance grows linearly and directly proportioned to the size of input data.
* **O(N<sup>2</sup>)** - an algorithm whose performance is directly proportional to the square of the size of the data. Commonly seen in nested iterations.
* **O(2^N)** - algorithm whose growth doubles with each added data set. Also referred to as exponential growth.
* **O(log N)** - algorithms that rise sharply in time to time to execute, but level off as more and more data is added. Example from the reading: "a data set containing 10 items may take 1 second, 100 items takes 2 seconds, and 1000 items takes 3 seconds". Logarithmic growth of complexity, and often a highly efficient design for scalable algorithms. 