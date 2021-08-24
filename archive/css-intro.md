# Intro to CSS

CSS (**C**ascading **S**tyle **S**heets) is used to change how a wesite *looks*. It is used in combination with HTML, which controls the structure of a website. HTML has a universal default style that applies to each element, but with CSS we can make a website look much more unique.

## CSS Syntax

CSS is a **rule based language**, meaning you define rules and those rules are then applied to an HTML document. The following is an example of how CSS should look:

```CSS
h1 {
    color: red;
    font-size: 5em;
}

p {
    color: black;
}
```

In CSS, we first define the element that we want to syle (h1 or p, in the example). We then open up curly brackets and state **property and value pairs** in accordance with the style we want to achieve. Our example above will style h1 to be colored red and 5 times the standard font size. It will also style p to be colored black.

## CSS Modules and Specifications

CSS contains a massive library of properties. As a result, the language is broken up into more digestable **modules** that contain related properties. An example of this is the *Backgrounds and Borders* module which contains the `background-color` and `border-color` properties.

All web standards technologies are contained in large documents called **specifications**. These are published and maintained by various standards organizations, such as W3C, WHATWG, ECMA, or Khronos. While these are mostly for engineers, it's good to know they exist. CSS specifically is developed by the [CSS Working Grounp](https://www.w3.org/Style/CSS/), a group from within the W3C.

## Browser Support Information

Since CSS is constantly being developed and added to, not all browsers will always support the latest and greatest CSS property. When developing make sure to double check that your site will be compatible with as many browsers as you can, and have a backup in case something is incompatible. The MDN reference for each CSS property will state the browser compatibility for the latest version of each browser, so be sure to double check!

## Adding CSS to an HTML Document

There are 3 main ways to actually **use** CSS:

### 1. External CSS

External CSS refers to using a separate .css file, commonly called a "style sheet," to assign CSS properties to the elements of an HTML file. To reference an external CSS file, you will use the `<link>` element and define `rel=""` and `href=""` attributes. All the CSS properties will be in the .css file that you reference, and won't gum up the lines of your HTML code.

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="mystyle.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

### 2. Internal CSS

Internal CSS refers to using the `<style></style>` element inside the head section of your HTML to apply style properties to elements. It takes up more space in your HTML file, but should generally be contained within the `<head></head>` element. This keeps things from getting too messy in your HTML file.

```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

### 3. Inline CSS

Inline CSS refers to using the `style=""` attrubite inside of individual elements of your HTML file. This is generally the least preferred execution of using CSS, but does work and can be nice for experimentation when decidign on styles. Multiple property-value pairs can be used inline, provided they are separated by a semicolon.

```html
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```


## Order of application

Since there are 3 entirely different ways to apply style, there will be times when styles overlap with each other. When this happens, the **last style applied** is the one presented to the user. In the below example, the inline style of the h1 element will be applied over whatever is defined in the mystyle.css stylesheet. If you end up mixing different executions of CSS, pay close attention to the order that styles are applied to your HTML document.

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
<style>
h1 {
  color: orange;
}
</style>
</head>
```

## A Note on Colors

The `color` property of CSS defines the color of text. This sounds simple enough, but there are many different types of values that the `color` property will accept:

- Hex:

    ```CSS
    body {color: #92a8d1;}
    ```

- RGB:

    ```CSS

    body {color: rgb(201, 76, 76);}
    ```

- RGBA:

    ```CSS
    body {color: rgba(201, 76, 76, 0.6);}
    ```

- HSL: 

    ```CSS
    body {color: hsl(89, 43%, 51%);}
    ```

- HSLA

    ```CSS
    body {color: hsla(89, 43%, 51%, 0.6);}
    ```

Experiment with CSS colors, and check out color references like the one availale from [Adobe](https://color.adobe.com/create/color-wheel)

References:<br>
[MDN What is CSS?](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/What_is_CSS)<br>
[W3Schools How to Add CSS](https://www.w3schools.com/css/css_howto.asp)<br>
[W3Schools color Property](https://www.w3schools.com/cssref/pr_text_color.asp)
