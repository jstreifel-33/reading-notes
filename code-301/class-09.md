# Functional Programming

## Functional Programming Concepts

Source *(article)*: [Concepts of Functional Programming in Javascript](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

* **What is functional programming?**
  * Per [Wikipedia](https://en.wikipedia.org/wiki/Functional_programming): Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.
* **What is a pure function and how do we know if something is a pure function?**
  * A pure function is a function that does not rely on external objects. It always returns the same value, when passed the same parameters. Pure functions also cause no observable side effects, such as modifying global variables.
* **What are the benefits of a pure function?**
  * Pure functions are stable, consistent, and predictable. This allows ease of testing, since we can always pass information to a function alone for testing. No external process need to be performed first.
* **What is immutability?**
  * Immutability is used to describe something that does not change over time and cannot be changed after creation.
* **What is Referential transparency?**
  * Referential transparency is the combination of immutable data, and pure functions. If we know our inputs will never change, and we know our function always returns the same value given the same inputs, we can essentially replace the function call using known inputs with the return value of the function. **The return value will not change, on the merit of immutability and pure functions.**

## Modules and Require()

Source *(Youtube)*: [The Net Ninja: Node JS Tutorial for Beginners #6 - Modules and require()](https://www.youtube.com/watch?v=xHLd36QoS4k)

* **What is a module?**
  * A module is a method or function that you can export from one .js file for use in another .js file.
* **What does the word ‘require’ do?**
  * `require(path)` finds the specified file passed as an argument, and returns whatever method or function is exported from that file.
* **How do we bring another module into the file the we are working in?**
  * Using `require('path)`!
* **What do we have to do to make a module available?**
  * To make an imported module available for use, we must assign the return value of require to a variable, like so: `const extFun = require('./path/extFun')`. This will make the `extFun` module available for use in our current file.

## Things I want to know more about

So referential transparency is a super cool topic that I hadn't considered before. I understand the underlying concept of it, but how can this be applied to the work that we do as developers? It's had to imagine where subbing out entire functions for their returns would really make my life any easier, given the work we've been doing so far. What approach should we take if we incorporated pure functions and immutable state into our projects?
