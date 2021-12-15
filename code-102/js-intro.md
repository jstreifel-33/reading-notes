# Introduction to Javascript

JavaScript, or JS, is most widely used for programming how web pages behave. It also has applications outside of web development, such as it's use in Node.js and Adobe Acrobat.

## What is JavaScript

| Characteristics | Styles |
|---|---|
| Prototype-Based | Object-Oriented |
| Multi-Paradigm | Imperative |
| Single-Threaded | Declarative |
| Dynamic | |

JavaScript is based on the ECMAScript Language Specification [ECMA-424](https://tc39.es/ecma262/) and the ECMAScript Internationalized API Specification [ECMA-402](https://tc39.es/ecma402/).

**NOTE:** JavaScript and Java are not the same, and should not be confused.

## Using JavaScript

JavaScript can be placed in HTML using the `<script></script>` element. It can also be called from an external .js file by adding the `src=""` attribute to the `<script>` element. Javascript itself has many functions and behaves by rules different from HTML rules.

## Variables

Javascript uses variables to store and pass information around. A variable can be declared using `var`, `const`, or `let`. Variable names are unique identifiers which are case sensitive and cannot be the same as existing reserved words (such as keywords for JavaScript).

An example of declaring variables with `var` would be:

```js
var x = 5
var y = 7
var z = x + y
```

In this code we declare our x and y variables, and declare a third variable z as the sum of x and y.

Variables can also be strings of text `var name = "John"` which can be added together using the + operator.
