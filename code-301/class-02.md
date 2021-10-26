# React States and Props

## React Lifecycle

Source *(Blog Post)*: [React: Component Lifecycle Events](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)

* **Based off of the diagram from reading, what comes first, the 'render' or the 'componentDidMount'?**
  * The 'render' will happen first. This occurs in the "Render Phase" which is the first of 3 phases in the React lifecycle: **Render**, **Pre-Commit**, and **Commit**. 'componentDidMount' occurs at the end of the "Commit Phase."
* **What is the very first thing to happen in the lifecycle of React?**
  * The very first thing to happen will be the Constructor method. This occurs when a component is created and inserted into the DOM and is followed by other methods during mounting.

* **The following things happen in the following order:**
  1. constructor - happens before mounting and initializes component.
  2. render - the only required method. Examines state and props and and sends them to the DOM.
  3. componentDidMount - invoked immediately after mounting. This is where information for network requests or initializing the DOM should be placed.
  4. React Updates - after any state changes, React will update content of mounted components.
  5. componentWillUnmount - method for cleaning up the DOM and network requests after tasks have completed.

* **What does componentDidMount do?**
  * componentDidMount fires off immediately after a component is mounted. It can be used to perform necessary network requests to update state, or for re-initializing the DOM if necessary. A components state can also be changed in componentDidMount if necessary.

## React State Vs. Props

Source *(Video)*: [Web Dev Simplified: React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJI)

* **What types of things can you pass in the props?**
  * Props can generally be used to pass any traditional data between components. This can be objects, strings, numbers, or booleans.
* **What is the difference between props and state?**
  * Props are information passed from one component into another. This differs from state in that state is self contained and generally does not affect other components. State change can, however affect the values of props that one component may be sending out to another.
* **When do we re-render our application?**
  * Re-render occurs anytime there is a state change in a component. This re-render can be component specific and doesn't necessarily refresh a wep page or app.
* **What are some examples of things we could store in state?**
  * State can store information that will be managed internally by a component. The video used the example of time within a timer, but we could also store things like login status or the setting of a page's light/dark mode.

## Things I want to know more about

The way that props and state work feel reminiscent of events in traditional JS, and I want to learn more about how dynamic information/events behave within the prop/state ecosystem. I know that information flows downward in React, but I don't know yet how components lower in the tree can 'ping' components higher in the tree to trigger a cascading state change of flow of new information.
