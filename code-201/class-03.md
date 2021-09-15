# HTML Lists, the CSS Box Model, and JS Control Flow

## HTML Lists

List elements are used to make lists!

* `<ol>` & `<ul>` - ordered list and unordered list, respectively. One is numbered and the other isn't. both use th `<li>` element for their actual list items.
* `<dl>` - a **definition list** is used to list terms and their definitions. Inside of a `<dl>` element, `<dt>` is used to indicate the term being defined and `<dd>` is used to indicate the definition.

NOTE: lists can be nested within each other, and nested lists will be indented past their parent.

```html
<ul>
    <li>Dogs</li>
        <ul>
            <li>Poodle</li>
            <li>Husky</li>
            <li>Doberman</li>
    <li>Cats</li>
        <ul>
            <li>Maine Coon</li>
            <li>Bengal Cat</li>
            <li> Scottish Fold</li>
    <li>Birds</li>
        <ul>
            <li>Canary</li>
            <li>Parrot</li>
            <li>Finch</li>
```

## CSS and Boxes

CSS treats HTML elements as if they have boxes around them. With this in mind, there are many properties we can use to affect the size of the boxes containing our HTML

* `width``height` - Used to change the dimensions of an element. Can be set with absolute value (px) or with relative values (% and em).
* `min-width``max-width` - Used to set a minimum or maximum width for an element. Using absolute values for these can be useful for anticipating visibility on different display sizes.
* `min-height``max-height` - Much like their width counterparts, these can be used to set height bounds.
* `overflow` - tells the browser what to do when content is too large for the bounds of a element. Can be given the values `hidden` and `scroll`

Borders, margins, and padding are the space between your content and the content around it. These can be manipulated to give your page a sense of organization and utilize "white space."

* **Borders** can be modified using `border-width`, `border-style`, and `border-color`. All these can also be assigned as once using the shorthand `border` property: `border: solid thin black;`
* **Padding** is the space between content and the border. The size of padding can be changed all at once or per side using `padding-top` `padding-right` `padding-bottom` and `padding-left`.
* **Margin** is the outermost space on an element, between the border and other margins. It can be controlled similarly to padding.

The `display` property can make inline elements act as blocks, or blocks act as inline. There is even `display:inline-block` that allows an element to act as inline, while retaining some properties of a block element.

Boxes can be hidden using the `visibility` property. Acceptable values are `hidden` and `visible`.

## Arrays

Arrays are special variables that store multiple values. Imagine an array as a list, indexed from 0. The length of an array (how many values are stored) can be found using the `.length` keyword. 

Arrays can be assigned using a literal assignment of an the array constructor.

```js
//creating an array using literal assignment
let fish = ['salmon', 'minnow', 'carp'];
return fish[0]; //returns 'salmon'
//creating an array using the Array constuctor
let mammals = new Array('whale','dolphin','seal')
return mammals[2]; //returns 'seal'
```

After an array has been defined and assigned values, new values can be assigned to any position using an assignment operator `=`.

```js
let fish = ['salmon', 'minnow', 'carp'];
fish[1] = 'trout';
return fish[1]; //returns 'trout' instead of original value of 'minnow'
```

## Control Flow

``If...else`` statments can be used to make decisions in JavaScript. `if(conditional)` evaluates the provided condition, and if true the code within the if statement executes. `else` can be used following `if` to provide an alternative if the condition evaluates to false. `else` can be followed by another `if(condition)` statement as well to create cascading decision trees.

**Switch statements** can be used as an alternative to if statements in the case that you have expected inputs. A switch statement will recieve an input and evaluate it against cases looking for a match. The code below the matching case will execute, and `break;` will exit the switch statement. A default is run is no cases are found to match.

```js
switch(dogBreed){
    case 'labrador':
        alert("Cool labrador!");
        break;
    case "pitbull":
        alert("Cool pitbull!");
        break;
    case default
        alert("I don't know that dog breed, but it looks cool!");
        break;
}
```

### Truthy & Falsy

`true` and `false` are the two boolean values, but other values can be evaluated to be true or false. We call these truthy and falsy evaluations. Values that evaluate to false are:

* `false` - the traditional false boolean
* `0` - the number zero
* `" "` - an empty string
* `NaN` - the NaN value. This is returned when expected output is a number but a number is not provided.
* `var empty` - a valiable that has been declared but not assigned.

Pretty much everything else is **truthy.**

### Loops

Loops check a condition and execute code accordingly.

**For** loops are used to run a set of code a specific number of times. The contain an initialization to assign a variable, a condition to be evaluated, and an expression to perform after each loop. The loop will run until the condition provided evaluates to false. **Be mindful to avoid infinite for loops**.

```js
//for(assignment; condition; expression){code}
for (var i = 0; i < 3; i++){ //the code will execute 3 times.
    alert("This is loop " (i+1));
}
```

**While** loops run repeated until a provided condition is false. They are useful for when you're not sure how many times a loop will need to run.

**Do while** loops are similar to `while` but will run the assigned code at least once before evaluating the provided condition.

Loops use two keywords:\
`break` causes the loop to terminate and the code will move to the next line of code outside of the loop.\
`continue` causes the current iteration of the loop to stop and the condition is evaluated again.
