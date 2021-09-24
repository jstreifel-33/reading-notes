# JS Error Handling and Debugging

JavaScript executes code line-by-line. When it encounters a place where data is needed from a function, it pauses execution and begins the called function. this can happen multiple times before resolution, leading to a "stack" of Javascript waiting on other code to execute. Each stack is what is known as an **execution context**.

Each execution context consists of 2 phases:

1. **Prepare Phase** - creates a new scope and declares variables, functions, and arguments.
2. **Execute Phase** - Assigns values to variables, references functions and runs their code, executes statements.

Function and variable declarations are **hoisted**, which means they are executed before any other code. This makes it possible to call a function above the declaration, provided that it is defined by a declaration and not an expression.

**Errors** come in many different types, and there are generally 2 things a dev can do with errors:

1. **Debug** the script. This involves tracking down and eliminating the source of the error. In browser developer tools, errors will be accompanied by a line number, which can often provide insight into what went wrong.
2. **Handle Errors** gracefully. Sometimes an error isn't the fault of code. Server errors can't be helped by debugging, so in cases like this it's important to write error-handling code.

The `console.log` method can be used throughout code to verify that different sections are working as expected. By tracking our code results we can narrow down where a bug is originating if it isn't immediately clear from the error. `console.info()`, `console.warn()`, and `console.error()` can also be used to create differently flagged messages to the console for better tracking of code flow.

`console.group()` can be used to return multiple lines of messages together. `console.groupEnd()` is used to indicate the end of a console group.

`console.assert()` can test if a condition is met, and log a message if found false.

**Breakpoints** can used in developer tools to stop code and check variables at that point in execution. JS also includes the `debugger` keyword which is automatically create a breakpoint if executed in developer tools.

**Handling Exceptions** is done with the `try...catch...finally`. Each keyword uses a code block.

```js
try (
  //Try to execute
) catch (exception) {
  //If exception, catch executes
} finally {
  //Finally always executes
}
```

This allows us to create error messages to inform the user in places where we believe errors will occur outside of our control. When `try` experiences an error, the error object will be passed to `catch` and can be used to code a course of action. `finally` will always run regardless and is often used to clean up after the previous two clauses.

`throw new Error('message')` can be used to create custom errors in areas where you anticipate errors. It allows for more descriptive error messages instead of the defaults provided by JS.
