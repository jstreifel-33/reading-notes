# Basics of HTML, CSS, and JavaScript

## Text in HTML

When creating content with HTML, there are multple elements that can be used to contain text:

* `<h1>``<h2>``<h3>``<h4>``<h5>``<h6>` - The **heading** element has 6 different levels and is used to indicate various levels of headings.
* `<p>` - The **paragraph** element is used to contain paragraphs. Different `<p>` tags will separated by a line break.
* `<b>` & `<i>` - In-line tags used to apply bold and italics to text.
* `<sup>` & `<sub>` - In-line tags used to apply superscript and subscript to text.
* `<br />` & `<hr />` - `<br />` is used to create a line break in a document, and `<hr />` is used to create a break between themes using a horizontal rule.

**Semantic elements** are used to add extra information to web page without affecting structure.

* `<strong>` - Used in-line to indicate that content has strong importance. Effectively bolds text.
* `<em>` - Used in-line to indicate subtle emphasis. Effectively italicized text.
* `<blockquote>` - Used for longer quotes that take up a paragraph. Still requires a `<p>` tag for text.
* `<q>` - Used for shorter quotes that are contained paragraphs. Both this and `<blockquote>` may use the `cite=` attribute to indicate source.
* `<abbr>` & `<acronym>` - Used to contain abbreviations and acronyms. The `title=` attribute can be used to indicate full text that will be shown when the user mouses over the content.
* `<cite>` - Used to reference a piece of work, such as a book, film, or research paper.
* `<dfn>` - Used when a term (technical jargon, etc.) is defined for the first time.
* `<address>` - Used to contain contact information for the author of a page.
* `<ins>` & `<del>` - Shows text that has been inserted and deleted from a document. Underlines and strikes through, respectively.
* `<s>` - Indicates irrelevant text that should not be deleted from the document. Also strikes through.

## Introducing CSS

CSS (Cascading Style Sheet) code is used to apply style to elements, affecting their visual appearance. The **cascading** quality means that CSS is applied from top to bottom in a document. If multiple styles are applied to a single element, class, or ID, the last style is the one that takes precendence, from top to bottom.

There are multiple ways to apply CSS to an HTML file.

* External CSS - `<link>` can be used to link to an external .css style sheet. Inside the `<link>` tag, set `href="/location/stylesheet.css"` `type="text/css"` and `rel="stylesheet"`.
    * Useful for styling multiple pages of website to look the same.
* Internal CSS - `<style>` can be used to write CSS style sheet within an HTML document. Additionally, the attribute `style="selector:value"` can be used inside of the opening tag of an element.
    * More ideal for styling a single page.

## Basic JavaScript

JavaScript is used to write a series of instructions for a computer.

JavaScript stores information in **variables**.

Before a Variable can be assigned a value it must be **declared** using `var` or `let`. Variables can be both declared and assigned in the same line of code.

```js
var ageMonths = 8;
let breed = "labrador";
//variables can be declared without values and will be undefined until assigned a value.
var name;
```

Variables can store numbers, strings, or booleans. At any time, the `typeof` operator can be used to determine the datatype of a variable.

An **array** is a special type of variable used to store multiple values. Arrays are indexed starting at 0.

```js
var breeds = ['labrador', 'terrier', 'rotweiler'];
return breeds[0]; //returns 'labrador'
return breeds[1]; //returns 'terrier'
return breeds[2]; //returns 'rotweiler'

//values can be reassigned in an array
breeds[1] = 'poodle'
return breeds[1] //returns 'poodle'
```

## Decisions and Loops

Decisions are made in JavaScript using conditional statements and comparison operators.

Comparison operators include:

* `==` "is equal to" checks if values of two operands are equal.
* `===` "strict equal to" compares value **and** datatype of two operands.
* `!=` "is not equal to" evaluates true if values of two operands are not equal.
* `!==` "strick not equal to" evaluates true if value **and** datatype of two operands are not the same.
* `>``<``>=``<=` "greater than, less than, greater than or equal to, less than or equal to" are all used to compare the left operand to the right operand. Evaluate true or false.

Logical operators can be used in conjuction with comparison operators to create more complex conditional statements.

* `&&` logical AND - evaluates to true if both left and right operands evaluate to true.
* `||` logical OR - evaluates to true if **either** the left or right operands evaluate to true.
* `!` logical NOT - takes a single boolean and inverts it. `!(1==2)` evaluates to true and `!(1==1)` evaluates to false. Can be used to create NAND and NOR logic.

Conditional statements can be used to make a decision in what is called an **if statement**. An if statement executes its contained script if the provided conditional statement evaluates to true. This can be used to create conditional flow within script.

```js
breed = ['labrador', 'terrier', 'rotweiler'];
dog1 = breed [0];
dog2 = bree[1];
//The following code will compare the breed of two dogs and alert the user of the result.
if (dog1 == dog2){
    alert('These dogs are the same breed!');
}else{
    alert('These dogs are not the same breed!');
}
```
