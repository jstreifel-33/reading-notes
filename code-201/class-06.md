# Problem Domain, Objects, and the DOM

## Object Literals

In JavaScript, an **object** is used to group together variables and functions into something that would resemble a model. When part of an object, variables and functions take on new names: **properties** and **methods**, respectively.

**Literal notation** is the most common way to create objects, and uses curly braces to contain the contents, separated by commas.

```js
let car = {
  make: 'Honda',
  model: 'Civic',
  mpg: 23.2,
  fuelGallons: 7,
  range: function(){
    return this.mpg * this.fuelGallons;
  }
};
```

Object properties and methods are accessed using dot notation, as seen in the above example. Square bracket syntax can also be used.

## Document Object Model

When a webpage is rendered, a model is stored called the DOM tree, which is stored in browser memory.

There are 4 nodes to consider that make up the DOM tree:

* The Document Node
* Element Nodes
* Attribute Nodes
* Text Nodes

Elements are always accessed through the `document` object. Elements can be selected by ID using the method `document.getElementById('someId');`.

Methods that can select multiple nodes, such as `document.getElementsByClassName('comeClass')`, return a NodeList, which is an object containing a collection of nodes indexed at 0 (similar to an array), in the order that they appear in the document. Individual nodes can be accessed from a NodeList using the `item()` method or array syntax, which is the preferred way of accessing them.

When working with a NodeList, the `.length` method can be used similarly to arrays for control of loops. This can allow the changing many Nodes at once.

### DOM Traversal

When a Node is selected, you can select another node using one of these 5 properties:

* `parentNode` - finds the parent element of the currently selected node.
* `previousSibling`,`nextSibling` - find the previous and next siblings of current node, if they exist.
* `firstChild`,`lastChild` - Find the first of last child of currently selected element, if they exist.

### Accessing and Updating Content

* `nodeValue` - retrieves or amends content of a node. Can be used with `=` to assign new value.
* `textContent` - retrieves or amends just the text of a containing element.

There are two way to add/remove content from the DOM:

`innerHTML` can be used on any element to retrieve/replace content. This allows the inserting of any HTML, assigned as a string. It is generally good practice to store the string in a variable first. **Using `innerHTML` presents sercurity risks, as it allows the inserting and retrieving of any HTML**

DOM Manipulators are the safer method, but it requires more code and can be slower. DOM manipluation involves building up DOM nodes piece by piece, and appending them together until they are where you want to place them. This would start with creating a text node, storing it in a variable, creating the containing node, placing your text node variable inside, etc. until the DOM is updated to as you want. This can prevent the inserting of new HTML tags, since you're starting with a **text** node.

From Duckett JS pg 223:

```js
let newText = document.createTextNode('quinoa'); //create the text
let newEl = document.createElement('li'); //create the new element
newEl.appendChild(newText); //append text node to new element
let position = document.getElementByTagName('ul')[0]; //specify where to place new element
position.appendChild(newEl); //append new element to desired parent
```

Removing an element using DOM manipulation:

From Duckett JS pg 225

```js
let removeEl = document.getElementsByTagName('li')[3]; //specify element you would like to remove
let containerEl = removeEl.parentNode; //store parent in variable.
containerEl.removeChild(removeEl); //use .removeChild method using new variables.
```

### Attributes and the DOM

* `getAttribute()` - Returns the value of an attribute
* `hasAttribute()` - Checks if element node has attribute. Returns boolean.
* `setAttribute()` - Sets the value of an attribute
* `removeAttribute()` - removes an attribute
* `className` - returns or sets value of a class attribute
* `id` - returns of sets value of id attribute
