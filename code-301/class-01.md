# Introduction to React and Components

## Component-Based Architecture

Source: [tutorialspoint: Component-Based Architecture](https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm)

### Questions to answer

01. What is a "component?"
    - A component is a modular, portable, reusable software capsule. It contains it's own functionality internally and can be exported to be used to interact with other components.
02. What are the characteristics of a component?
    - Reusability: usually designed to be used in multiple situations across an app.
    - Replaceable: can be easily swapped for other components
    - Not context specific: can operate in many different contexts
    - Extensible: can be extended from existing components (similar to classes)
    - Encapsulated: do not expose internal processes, variables, or state to rest of app
    - Independent: designed to have minimal dependencies on each other
03. What are the advantages of using component-based architecture?
    - Ease of deployment: easier to replace existing versions, since updated components will have minimal affect on other components.
    - Reduced Cost: third-party components can spread cost of development/maintenance
    - Ease of development: components provide defined functionality, allowing development without impacting the rest of a system
    - Reusable: components can be written once and used many times
    - Modification of technical complexity: complex operations can be performed inside of components
    - Reliability: reliable components form a reliable system. If one component fails, the whole system doesn't go down.
    - System maintenance and evolution: can be easily modified with minimal impact
    - Independent: components can be developed independently, increasing productivity

## What is Props and How to Use it in React

Source: [ITNEXT.io: What is "Props?"](https://itnext.io/what-is-props-and-how-to-use-it-in-react-da307f500da0#:~:text=%E2%80%9CProps%E2%80%9D%20is%20a%20special%20keyword,way%20from%20parent%20to%20child)
*(account required | possible paywall)*

Associated Youtube Video: [Cem Eygi Media: React Props](https://www.youtube.com/watch?v=M_Fmvs5CiDo)

### Questions to answer

01. What is "props" short for?
    - "Props" is short for "properties" and is a React keyword for passing data between components.
02. How are props used in React?
    - Props are used like attributes when calling a component, and like arguemnts when defining a component.

    ```jsx
    //childComponent can have prop values assigned to it when called by a parent
    //assignment is similar to HTML attributes but uses {}
    class parentComponent extends Component{
      render(){
        return <childComponent text={"Hello world"} />;
      }
    };

    //props is an object containing the prop values assigned to childComponent
    //assigned props are accessed using dot notation as seen below
    //maintaining consistency in naming convention is important
    let childComponent = (props) => {
      return <p>{props.text}</p>;
    };
    ```

03. What is the flow of props?
    - Prop data flows **down** from parent to child, and is read-only when passed to a component as an argument.

## Additional Notes

I have no notes.

## Things I want to know more about

Note that one component in the above example code uses class notation while the other uses arrow function notation. **As far as I can tell** these are different. The parent extends React.Component and the child acts simply as a functional component to accomplish a task (creating the `<p></p>` content). Both are still components, but the parent inherits the render() method, among other things, to allow for rendering to the app.

This might be a surface level understanding, so I want to know more about component instantiation and when each notation should be used to effectively build out the parts of an app.
