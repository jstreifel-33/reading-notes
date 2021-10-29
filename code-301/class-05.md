# React: Putting it all together

## Thinking in React

Source *(Docs)*: [reactjs.org - Thinking in React](https://reactjs.org/docs/thinking-in-react.html)

* **What is the `single responsibility principle` and how does it apply to components?**
  * The single responsibility principle is a programming rule that every function or class should be responsible for one function. With regards to components, this just means designing components to perform a single task. If components grow too large during design, they should be be decomposed into several smaller components.
* **What does it mean to build a static version of your application?**
  * Building a static application means building out the structure of an application without any interactivity. Designing both structure and dataflow at the same time can get unruly or frustrating, so decoupling these two processes can help smooth out the development process.
* **Once you have a static application, what do you need to add?**
  * After building a static application, you should identify the minimal state required for site data. Go through different data that you expect to work with and decide how you're going to store/calculate it. Data that will need to be stored for reference later without computation will generally be stored in state somewhere.
* **What are the three questions you can ask to determine if something is state?**
  1. Is the state passed in from a parent via props? If so, leave it as props, since it will be stored as state somewhere else.
  2. Does it remain unchanged over time? If so, it's probably not a state. Try defining a variable instead.
  3. Can you compute it based on any other state or props in your component? If so, it's not state. If you can compute it, generally you should.
* **How can you identify where state needs to live?**
  * Identify what data each component needs access to and find a common parent. If two or 3 components need access to imported data, the parent common to all three should probably be the one to store the data in state. It can be placed higher up if you'd like, but just remember: updating state re-renders a component and all of its children. There are time where re-rendering an entire page might not be the best or most efficient way to go about things.

## Higher-Order Functions

Source *(Online Textbook)*: [eloquentjavascript.net - Higher-Order Functions](https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK)

* **What is a "higher-order function?"**
  * A *higher-order function* is a function that either operates on other functions or receives other functions as an argument.
* **Explore the `greaterThan` function as defined in the reading in your own words, what is line 2 of this function doing?**
  * The greaterThan(n) function contains an arrow function with argument m, that evaluates m > n and returns the result. This can be used to modularly create functions through the assignment opperator.

  ```js
  //we first create a function that returns an arrow function
  function greaterThan(n){
    return m => m > n;
  }
  //we then invoke greaterThan and assign it's return
  let greaterThan20 = greaterThan(20);
  //evaluates to:
  greaterThan20 = m => m >20;
  //wow! we can now use this new function!
  console.log(greaterThan20(40));
  //prints true
  ```

* **Explain how either `map` or `reduce` operates, with regards to higher-order functions.**
  * `map` is considered a higher-order function because it receives a function as an argument, and applies it to the target of invocation. It essentially uses another function as a tool to be applied.

## Things I want to know more about

Are all function and methods that accept callback functions considered higher-order? I suppose it would make sense, but this is my first exposure to this concept. If so, it seems that JS has a pretty large amount of higher order functions and methods.

Also regarding thinking in React, it feels like this is one of the most crucial steps in creating an app. Without a solid plan it seems very easy to get "lost in the sauce." What methods have instructors or the cohort been employing or plan to employ for formulating an attack plan when designing React Apps or features? Personally I just scrawl out a draft with pen/paper. :)
