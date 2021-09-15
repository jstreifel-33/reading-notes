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

* `width``height` - Used to change the dimensions of an element. Can be set with absolute value (px) or with relative values (%).