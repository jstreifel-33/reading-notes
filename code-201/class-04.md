# HTML Links, JS Functions, and Intro to CSS Layout

## Links in HTML

Links are one of the most common features of the web, and allow for navigation between pages. This is accomplished with the `<a>` element.

```html
<a href="http://www.waysuperawesome.com">Visit my super awesome site!</a>
```

The `href` attribute is used to point to where you want the link to go, and the text inside the element is the text that will be hyperlinked. A full web address like the one above is knkown as a an **absolute URL**.

If you plan to link to a page within the same site, you can use an relative path instead, that simply points to where the page is in your file structure

```html
<a href="contact.html">Contact us!</a>
```

You can also create a link that addresses an email in the user's email program using `href="mailto:someone@email.com"`. To have a link open a new window use the `target="_blank"` attribute.

HTML ID's can be used to create links to different parts of pages.

```html
<a href="#recipe">Recipe</a> <!-- Will jump to the element with the "recipe" ID -->

<a href="index.html/#TOC">Table of Contents</a> <!-- Will jump to the "TOC" ID on page index.html -->
```

## Layout and CSS

Positioning schemes can be used to control how elements are placed on a page.

* `position:static` - the default way to treat HTML, blocks set to static will be stacked top to bottom.
* `position:relative` - let's you set the position of an element relative to where it would be in normal (static) flow.
* `position:absolute` - takes an element out of normal flow completely and allows it to be set in an absolute position.
* `position:fixed` - A type of absolute positioning that keeps an element in place even when the user scrolls.
* `z-index` - allows for overlapping elements. Elements with higher z-index properties will appear to be placed over those with a lower z-index property.
* `float` - Places an element to the far right or left of the containing element, allowing other content to flow around it.
  * Float can be used to cleverly tile elements, by setting width, margin, and padding, accordingly.
  * `clear` is used to ensure that boxes don't touch other elements on the right or left side.

**Layout Grids** can be used to give a clean and organized look to a site. It allows for grouping of elements inside similarly sized containers and breaks a page up into easily digestible parts. An example is the **960 Grid** which has 12 columns accross a 960 px container. each column is 60 px wide with 10 px margins. This kind of grid is useful because 960 scales up to common resolutions cleanly, such as 1920x1080 and 3840x2160.

## Functions, Methods, and Objects Pt.1

Functions allow the grouping together of JavaScript statements, and are declared using the `function` keyword. After declaration, they can be "called" to execute using `someFunction(input)`. Functions can also be written to execute without requiring an input.

```js
//functions can be written to require no input
function helloWorld(){
  console.log("Hello World!");
}

//functions can be written to accept any number of inputs. The names for inputs can be used as variables within the function.
function mulitply(inp1, inp2){
  return inp1 * inp2;
}
```

## Paired Programming and Why

**Paired Programming** is a process for writing code where two people work together as a team on the same project. One person acts as the "Driver" who handles the mechanics of writing code, and other as the "Navigator" who conceptualizes, watches for bugs/typos, and looks up references throughout the coding process. Paired programming is a process that puts the "two heads are beter than one" addage to use.

So, why paired program? A few reasons:

1. Greater efficiency - two people focusing on the same code base helps things move along faster, and shortens the length of hang-ups.
2. Engaged collaboration - working with a partner can be more engaging for programmers and helps people retain focus. It also teaches programmers to assist each other an ask for assistance when needed.
3. Learning from fellow students - Everyone has a different approach to problem solving, and close collaboration can expose programmers to new ideas and methods for approaching problems.
4. Social skills - Pair programming improves social skills. Communicating with another person through a process helps us learn how to convey thoughts about coding in a coherent manner.
5. Job interview readiness - A common interview step is paired programming between a current employee and an applicant. Practicing this process will help prepare a programmer for a paired programming interview, if the event arises.
6. Work environment readiness - Many companies utilize pair programming to train fresh hires on how they operate. Getting comfortable with a pair programming setting early can help programmers hit the ground runnign upon being hired.

Source: [6 Reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)
