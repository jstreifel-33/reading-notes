# Getting Started with HTML

## Wireframes

[Reference: The Definitive Guide: How To Make Your First Wireframe](https://careerfoundry.com/en/blog/ux-design/how-to-create-your-first-wireframe/)

### What is a Wireframe?

The purpose of a **wireframe** plan how information will be presented on your website. A good website should be easy to navigate, regardless of fancy colors and texts.

Wireframing can be accomplished **by hand** usign a whiteboard or piece of paper, or **in software** using one of the many online tools available. Wireframing by hand has the added benefit of being **easy to change** when consulting with a customer or focus group.

The overall process for creating website is inherently flexible and can be accomplished in a number of different steps. As shown in our reading the process can vary:

- Wireframe > Interactive Prototype > Visual > Design > Code
- Sketch > Code
- Sketch > Wireframe > Hi-Def Wireframe > Visual > Code
- Sketch > Wireframe > Visual > Code

### 6 Steps to make a Wireframe

1. **Do your research** - Before you even start is imporant to do two things: **understand your audience** by defining use cases and requirements, and **complement this undertanding wiht industry research**. Look at who your project is for, as well as what other successful apps and websites are doing. Don't be afraid to look at successes outside of your industry as well. A dieting app may have an interesting apporach to presenting user data!

2. **Prepare your research for quick reference** - Boil down all your data into an easily referenced cheat sheet to help guide you as you design. Take note of the biggest requirements, or some quotes that stood out from what the users or customers want out of your product.

3. **Map our user flow** - Ensure that you've planned out how users will navigate through information and different screens. You want the path users take to be intuitive and simple. If they want to find a tool or piece of information, it should be easy to access, and easy to return from!

4. **Draft, don't draw. Sketch, don't illustrate** - Put pen to paper, but focus on function. Organize where information will be presented, not what it will look like. As you work, consider the following points:
   - How can you organise the content to support your users’ goals?
   - Which information should be most prominent? Where should your main message go? 
   - What should the user see first when arriving at the page?
   - What will the user expect to see on certain areas of the page?
   - Which buttons or touch points does the user need to complete the desired actions?

5. **Add some detail and get testing** - Begin adding informational detail to your wireframe, preparing it for usability testing. Work from top-to-bottom, left-to-right as you go. Consider the following as you work:
   - Usability conventions, such as putting the navigation at the top next to your logo, having a search box on the top right, and so on
   - Simple, instructional wording for i.e. calls-to-action
   - Trust-building elements: What do you need to build trust in your customers and where would be the best place to put these elements?
   - Tooltips to indicate any functionality that could be included in a prototype transition
Once you've finished adding informational details, proceed with usability testing. You can use colleagues, or online tools like [Prott](https://prottapp.com/) or [Usability Hub](https://usabilityhub.com/)

6. **Start turning wireframe into prototype** - In this step you'll be creating a more high fidelity prototype, using the feedback you received during the usability testing. There are many tools you can use, with the most popular being Sketch and Figma.

When wireframing a website, remember the three biggest keys: **Clarity, Confidence, and Simplicity**

## HTML Basics

[Reference: HTML Basics by Mozilla](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)

### Elements

HTML (**H**yper**t**ext **M**arkup **L**anguage) is the code used to structure a webpage and its content.

HTML is made up of **elements** like the one below:

```html
<p class="editors-note">My cat is very gumpy</p>
```

An **element** consists of an opening and closing **tag** (`<p></p>` in this case), **content** (My cat is very grumpy), and **attributes** (`class="editors-note"`).

**Note**: Some elements do not require content, and are referred to as "empty elements." An exampl of this is the `<img>` element.

### Anatomy of an HTML Document

The following is an example of a basic html page code:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image">
  </body>
</html>
```

In this code we see the following elements:

- `<!DOCTYPE html>` - Ensures the document behaves correctly. Used to serve another purpose in the 1960's but that isn't relevant now.
- `<html></html>` - Wraps the entire page. Is referred to as the "root element"
- `<head></head>` - Container for stuff that you *don't* want to be showed to the viewer on the webpage. This includes keywords and text to be displayed on a browser tab.
- `<meta charset="utf-8">` - Sets the character set to UTF-8, which should handle any text you try to display.
- `<title></title>` - Sets the title of the page, which is displayed in the browser tab text.
- `<body></body>` - Contains all the content you want to display to the user who visits your webpage.

### Images

Images use the `<img>` element, like so:

```html
<img src="images/firefox-icon.png" alt="My test image">
```

In this example, we are trying to display the image "firefox-icon.png" ot the user. The attribute `alt="My test image"` is text used in place of the image if it fails to load properly. The alt attrubute is also used by text-to-speech software for the vision impaired to descibe your image, so use descriptive text whenever you can.

### Headings

HTML has 6 heading levels, `<h1>` - `<h6>`, used to organize your webpage:

```html
<h1>My main title</h1>
<h2>My top level heading</h2>
<h3>My subheading</h3>
<h4>My sub-subheading</h4>
```

Plan to use 3 or 4 levels of heading at most, as levels 5 and 6 are rarely used and can lead to a confusing webpage flow.

### Paragraphs

As we saw before, the `<p></p>` element is used for paragraphs. This will be one of the most commonly used elements for text content.

### Lists

HTML support **ordered lists** `<ol></ol>` and **unordered lists** `<ul></ul>`. List elements will be indicated by the `<li></li>` element, regardless of list type:

```html
<p>At Mozilla, we’re a global community of</p>

<ul>
  <li>technologists</li>
  <li>thinkers</li>
  <li>builders</li>
</ul>

<p>working together ... </p>
```

### Links

Links use the element `<a>`, short for "anchor." The content of the `<a>` element will be the text you want to act the link, and the `href` attribute (short for hyperlink reference) will direct where the link leads to.

```html
<a href="https://www.mozilla.org/en-US/about/manifesto/">Mozilla Manifesto</a>
```

### Semantics

It's important to use the right tool for the job. While the `<h1></h1>` tag will apply a certain style to text, the following will basically do the same:

```html
<span style="font-size: 32px; margin: 21px 0;">Is this a top level heading?</span>
```

It is important to remember, however, that the `<h1></h1>` tag will also assign a meaning, or **semantic value**, to your text of "a top level heading on the page." This might make a difference in how certain tools or searches interpret your page, so make sure you use the right elements for what you want to indicate on your page. Rely on CSS instead for stylistic decisions.

For a reference of elements with semantic values, refer to this link: [Mozilla HTML Elements Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

Additional reference page for HTML information:
[Mozilla HTML References](https://developer.mozilla.org/en-US/docs/Web/HTML)