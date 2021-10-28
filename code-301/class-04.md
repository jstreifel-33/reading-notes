# React and Forms

## Forms in React

Source *(Docs)*: [React Docs: Forms](https://reactjs.org/docs/forms.html)

* What is a 'Controlled Component'?
  * A controlled component is an input element whose value is controlled by React state. The state acts as the "single source of truth."
* Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why?
  * We should store them as soon the user enters them. This allows the parent component state to act as a single source of truth and share user entry with the rest of the page as they type. This enables functionality like search suggestions and auto-autocomplete.
* How do we target what the user is entering if we have an event handler on an input field?
  * We can use the onChange event within an input tag. This will activate the associated handler whenever the user changes the content of an input field. In the case of the docs example a handler updates the state in real time as user input occurs.

  * From reading source:

  ```jsx
  handleChange(event){
    this.setState({value: event.target.value});
  }
  <input type="text" value={this.state.value} onChange=this.handleChange>
  ```

  * The above code keeps the state updated as a user input text, and uses the state as value for the form upon submission. This is what's meant by using the state as a "single source of truth"

## The Conditional (Ternary) Operator

Source *(article)*: [codeburst.io - Ternary Operator](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)

* Why would we use a ternary operator?
  * A ternary operator is a more concise way of writing if/else statements, and can save time and space within our code.
* Rewrite the following statement using a ternary statement:

  ```js
  if(x===y){
  console.log(true);
    } else {
  console.log(false);
    }
  ```

  ```js
  //Refactored:
  x === y ? console.log(true) : console.log(false);
  ```

## Things I want to know more about

The reading about forms made decent sense up until handling multiple inputs. My understanding is almost there, but my brain might be fried for the day. I'll need to revisit handling multiple form inputs tomorrow with fresh eyes to parse more meaning out of it, since I don't quite feel like I could implement it right now after completing the reading.

I do like the use of state for forms, though. I feel like it explains why input fields occasionally lag on input. Is that due to the state taking time to update? If so is the user input 'invisible' but being processed before rendering the updated form?
