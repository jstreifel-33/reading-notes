# Operators, Loops, and Iteration

## Operators

For notes on operators, refer to my programming notes: [Programming with JavaScript](archive/js-programming.md)\
MDN Reference: [MDN Javascript Guide: Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)

## Loops

Reference: [MDN JavaScript Guide: Loops and iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for_statement)

Loops are the programming way of performing a task repeatedly. There are various loop mechanisms for starting and stopping a task, such as specifying a number of times to run or running until a condition is met.

### `for` Statement

A `for` loop repeats until a specified condition evaluates to `false`. The syntax is:

```js
for ([initialExpression]; [conditionExpression]; [incrementExpression]){
  statement
}
```

The execution of a `for` loop is as follows:

1. The initializing expression is executed. Variables can be declared in this expression.
2. The condition expression is evaluated. If found to be true, the loop statement executes. If found to be false, the loop terminates.
3. Statement execution. Statements can be contained to a block `{}`.
4. If present, increment expression is executed.
5. Control returns to Step 2.

### `do...while` Statement

A `do...while` statement repeats until a specified condition evaluates to false. Syntax:

```js
do
  statement
while (condition);
```

**The statement is always executed once before the condition is checked.** If `condition` evaluates to `true` the statement executes again. At the end of every statement execution `condition` is evaluated. If `false`, execution stops and control moves to the next statement following the `do...while` loop.

### `while` Statement

A `while` statement executes its statements as long as a specified condition evaluates to `true`. Syntax:

```js
while (condition)
  statement
```

**The condition test occurs before the statement is executed**. If `true`, the statement is executed and `condition` is evaluated again. If false, execution stops and control moves to the next statement following the `while` loop.