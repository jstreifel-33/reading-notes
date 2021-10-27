# Passing Functions as Props

## Lists and Keys

Source *(docs)*: [React Docs: Lists and Keys](https://reactjs.org/docs/lists-and-keys.html)

* **What does `.map()` return?**
  * `.map()` returns an array containing the results of executing a callback function on each index of the array that the method is called on. Within React, it can be used to return an array of components or elements.
* **If I want to loop through an array and display each value in JSX, how do I do that in React?**
  * Use `.map()`. It can be used to generate and return an array of components or elements based on another array. This array of components can be assigned to a variable and called later using `{variable}` within the `render()` method.
* **Each list item needs a unique what?**
  * A unique **key** is required for each list item. this can be assigned using the `key='value'` attribute or prop. It's worth noting that keys only need to be unique among siblings.
* **What is the purpose of a key?**
  * Keys provide unique identities to list items. These keys are used to track which components are updated, removed, or added. Keys also give us a means of finding and extracting specific items from a list.

## The Spread Operator

Source *(blog post)*: [The Spread Operator (...) in JavaScript](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)

* **What is the spread operator?**
  * The spread operator `...arr` is a syntax that can be applied to an iterable object to split it into multiple arguments. It "spreads out" the information contained in an object.

* **List 4 things that the spread operator can do.**
  1. Copy an array
  2. Concatenate or combine arrays
  3. Add a state to React
  4. Convert NodeList to an array

* **Give an example of using the spread operator to combine two arrays.**
  
  ```js
  let peppy = ['do', 'a', 'barrel', 'roll!',];
  let slippy = ['enemy', 'shields', 'analyzed!'];

  let comms = [...peppy, ...slippy];
  console.log(comms);
  //returns ['do', 'a', 'barrel', 'roll!', 'enemy', 'shields', 'analyzed!']
  ```

* **Give an example of using the spread operator to add a new item to an array.**
  
  ```js
  let kongs = ['donkey', 'diddy', 'tiny', 'chunky'];

  kongs = [...kongs, 'lanky'];
  console.log(kongs)
  //returns ['donkey', 'diddy', 'tiny', 'chunky', 'lanky']
  ```

* **Give an example of using the spread operator to combine two objects to one.**

  ```js
  let samus = {
    variaSuit: true,
    armCannon: true
  };

  let mainDeck = {
    missileLauncher: true,
    morphBall: true,
    spaceJump: true,
    iceBeam: true
  };

  samus = {...samus, ...mainDeck};
  console.log(samus);
  //returns samus object
  //
  // {variaSuit: true,
  //  armCannon: true,
  //  missileLauncher: true,
  //  morphBall: true,
  //  spaceJump: true,
  //  iceBeam: true}

  ```

## Passing Functions Between Components

Source *(video)*: [How to Pass Functions Between Components](https://www.youtube.com/watch?v=c05OL7XbwXU)

* **In the video, what is the first step that the developer does to pass functions between components?**
  * The first thing to do is create the function that you want to pass. The function should be defined as a method of the parent whose state will be manipulated.
* **In your own words, what does the `increment` function do in the video demo?**
  * In the video demo `increment` uses an if conditional within `.map()` to search an array in the parent state for an object with a matching `name:` value. If matching, `increment` increases the associated `count:`property when invoked and returns a new array of objects, which is then assigns to the parent state in place of the original array.
* **How can you pass a method from a parent component into a child component?**
  * As a prop, just like any piece of data. `parFun = {this.parFun}` will pass the parFun method (this.parFun) as a prop from a parent to a child component.
* **How does the child component invoke a method that was passed to it from a parent component?**
  * The child component can invoke an inherited method using using `this.props.parFun()`, in the case of our example. The method is stored in the component's props so it is accessed the same way as any other prop.
  
## Things I want to know more about

The video didn't touch on passing functions down through multiple children, which I'm curious about. I assume it's still like props but I just realize that I'm not sure how props do that either. Do they have to be passed through each consecutive child, or is there a way to bypass several "generations," so to speak?
