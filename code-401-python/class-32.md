# React II

More React Review, so refer to the docs:

* [Conditional Rendering](https://reactjs.org/docs/conditional-rendering.html)
* [Lists and Keys](https://reactjs.org/docs/lists-and-keys.html)
* [Forms](https://reactjs.org/docs/forms.html)
* [Lifting State Up](https://reactjs.org/docs/lifting-state-up.html)
* [Composition vs Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
* [Thinking in React](https://reactjs.org/docs/thinking-in-react.html)

"Thinking in React" makes some good points. Don't be afraid of being formulaic in your approach. Recommended steps:

1. **Start with a Mockup** - Imagine you already have an API feeding you all the data you need. How do you want to present it? Draw it out or model it in a whiteboard.
2. **Break up UI into a component hierarchy** - Look at your model and draw boxes around every component/subcomponent. Evaluate how your model can be broken down into smaller parts with single responsibilities.
3. **Build a static version in React** - Start slow. Make a static page in React that reflects what you want to present to the user. Don't worry about wiring up state and props and stuff. Just get the layout and look down. Componentize as necessary.
4. **Identify the minimal representation of UI state** - Think about the minimal amount of mutable state needed to bring functionality to your page. What do you expect to change frequently? What areas of the page will react to user input?
5. **Identify where your state should live** - React is about one-way information flow, so identify common points for storing information. Where are your junctions that will control flow of state?
6. **Add inverse data flow** - Now that you've picked a place for state to live, consider how downstream components will act upon state. Take the necessary steps to enable interactivity at the necessary levels down your state flow.

By this point, you should be pretty close to done with your app. Now style away.

It's worth noting that if you have a different process working for you, stick to it. These steps are just recommendations from the React docs for going from 0 to full app in easy to handle steps.

## Additional Resources

* [ui.dev comprehensive React guide](https://ui.dev/react/)
* [Tailwind heroicons](https://heroicons.com/)
