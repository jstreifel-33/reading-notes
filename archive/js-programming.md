# Programming with JavaScript

## Expressions and Operators

Reference: [MDC Javascript Guide: Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)

## Operators

JavaScript has binary, unary, and ternary operators.

A **binary** operator requires 2 operands:

```js
//operand1 operator operand2;
3 + 4;
x * y;
```

A **unary** operator only requires 1 operand:

```js
//operator operand;
//or
//operand operator;
x++;
++x;
```

### Assignment Operators

An assignment operator **assigns a value to its left operand based on the value of its right operand.** The simplest example of this is equal `=`.

JS also includes multiple **compound assignment operators** that serve as shorthand for operations. For an in-depth table listing of these operators, refer the reference document listed on this page.

### Return Values and Chaining

Assignments like `x = y` have a return value, which can be retrieved by assigning or logging the assignment.

```js
x = y //returns y;
x += y //returns x + y;
x **= y // returns x ** y;
```

Logical assignments return the value of the logical operation they perform.

**Note: Return values are always based on the operands' value before the operation.**

When chaining expressions, they evaluate **right-to-left**. This opposite from what we're used to. `w = z = x = y` is equivalent to `w = (z = (x = y))`

### Destructuring

The destructuring assignment makes it possible to extract data from arrays or objects. The syntax is similar to the construction of arrays, and allows for much simpler execution:

```js
var foo = ['one', 'two', 'three'];

// without destructuring
var one   = foo[0];
var two   = foo[1];
var three = foo[2];

// with destructuring
var [one, two, three] = foo;

```

### Operator Types

There are many different types of operators in JS. For a detailed look at the operators under each type, refer to the reference document. The types are as follows:

- **Comparison operator** - compares its operands and returns a logical value based on whether the comparison is true. Any data type can be used and JS will attempt to match the types up, with the exception of the `===` and `!==` operators.
- **Arithmetic operator** - takes numerical values (literal or variable) as operands and returns a single numerical value. Division by 0 produces infinity.
- **Bitwise operator** - treats operands as a set of 32 bits, rather than decimal,hexadecimal, or octal numbers. The decimal number nine is represented as 1001, for example. Bitwise operators return standard JS numerical values.
  - *Bitwise logical operators* - perform logical operations on numbers as 32 bit values. Each bit in the first operand is compared to the corresponding bit of the second operand.
  - *Bitwise shift operators* - take two operands. The first value is the quantity to be shifted, the second value is the number of bit positions to shift. `9<<2` evaluates to 36 (100100) by shifting 9 (1001) two bits left.
- **Logical operators** - typically used with Boolean values and return Boolean. `&&` and `||` can be used with non-Booleans since they return the value of one of the specified operands.
  - *Logical AND* `expr1 && expr2` - Returns expr1 if it can be converted to false; otherwise returns expr2.
  - *Logical OR* `expr1 || expr2` - Returns expr1 if it can be converted to true; otherwise returns expr 2.
  - *Logical NOT* `!expr` - Returns false if single operand can be converted to true; otherwise returns true.
- **String operators** - (+) can be used as a concatenation operator on strings. (+=) Serves a similar purpose, concatenating the second operand onto the first and storing the value.
- **Conditional (ternary) operator** - The only JS operator that takes three operands. The syntax is `condition ? val1 : val2`. If the condition is true of val1, val1 is returned; otherwise val2 is returned.
- **Comma operator** - (,) evaluates both operands and returns the value of the last operand. Generally this will be used in `for` loops and is regarded bad styel to use it elsewhere. As a general rule, outside of for loops stick to using 2 separate statements when necessary.
- **Unary operators** - Opertions with only one operand.
  - `delete` - deletes an object's property. Trying to access a deleted property will yield `undefined`.
  - `typeof` - returns a string indicating the type of the unevaluated operand.
  - `void` - specifies an expression to be evaluated without returning a value.
- **Relational operators** - compares operands and returns a Boolean value based on whether comparison is true.
  - `in` - Returns true if the specified property is in the specified object. `propNameOrNumber in objectName`
  - `instanceof` - Returns true if the specified object is of the specified object type. `objectName isntanceof objectType`

## Expressions

An expression is any valid unit of code that resolves to a value.

Javascript expressions are broken into categories:

- Arithmetic: evaluates to a number.
- String: evaluates to a character string.
- Logical: evaluated to true or false.
- Primary exrpressions: Basic keywords and general expressions in JavaScript.
- Left-hand-side expressions: Left values are the destination of an assignment.

## Functions

Reference: [MDN JavaScript Guide: Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)

Functions are essentially procedures in JavaScript. They take some input and produce an output based on a defined series of steps. Functions must be defined before they can be used.

Functions are defined using the `function` keyword:

```js
function square(somevar) {
    return somevar * somevar;
}
```

The function `square` above takes one input, assigns it to `somevar`, and returns the result of the expression `somevar * somevar`.

Defining a function does not execute it. A function must be **called** after being defined in order to execute. If we wanted to execute our above function on the value 2 we would use `square(2)` and it would return 4!

A function can also call itself, as seen in this example function for calculating a factorial:

```js
function factorial(n) {
  if ((n === 0) || (n === 1))
    return 1;
  else
    return (n * factorial(n - 1));
}
```

### Function Scope

Variables defined inside a function cannot be accessed outside of the function. A function can, however, access all variables and functions defined inside of the scope in which it is defined. Functions defined within functions can access all variables defined in the parent, as well as all variables that the parent has access to. This organizatoin of access is considered the **scope** of functions.

The existence of scopes allows for what are known as **closures**. Closures allow a sort of encapsulation of information, in case an inner function survives longer than the outer function. The following is an example from Mozilla:

```js
var pet = function(name) {   // The outer function defines a variable called "name"
  var getName = function() {
    return name;             // The inner function has access to the "name" variable of the outer function
  }
  return getName;            // Return the inner function, thereby exposing it to outer scopes
}
myPet = pet('Vivie');

myPet();                     // Returns "Vivie"
```

### Using the arguments object

`arguments[i]` is a JS object used to access the arguements of a function. The arguements of a function are stored as an array, so `arguments[0]` would be used to access the first input to a function. The total number of arguments can be indicated by `arguments.length`. This tool can be useful when you aren't sure many arguments will be passed to a function.

## Control Flow

Reference: [MDN Web Docs Glossary: Control Flow](https://developer.mozilla.org/en-US/docs/Glossary/Control_flow)

The control flow is the order in which a computer executes statements in a script.

Code is run in order from first to last line, unless a structure specifically changes the control flow, such as conditionals and loops.

Control flow is important to keep in mind when reading script. Don't just read top to bottom. Consider structures that change the control flow as you read.
