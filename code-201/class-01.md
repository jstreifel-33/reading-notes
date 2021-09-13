# Introductory HTML and JavaScript

## HTML

### Introduction

People access the web in a variety of different ways, including:

- Browsers: programs like Internet Explorer, Google Chrome, and Firefox. Viewing a webpage will usually require an address.
- Web Servers: special computers that are always connected to the internet. These host websites and when a browser goes to access a web page, it sends a request to a web server.
- Devices: Phones, tablets, smart tvs, laptop and desktop computers. People access the internet from a wide range of devices and it's important to keep these in mind.
- Screen Readers: programs that read the contents of a computer screen to the user. Keep accessibility in mind when designing a web page.

### Structure

Much like any other media, proper **structure** in a web page is important so that a user can easily understand and interact with you web page.

HTML Describes the **structure** of a website. It is made up of **elements** that act as containers for content, consisting of openening and closing **tags**. Some elements will be single tag, but generally content will have an opening and closing tag:

```html
<html>
    <head>
        <title>This is the title of your page, and will appear in the browser tab.</title>
    </head>
    <body>
        <p lang="en-us">The p element is used to create paragraphs!</p>
    </body>
</html>
```

The code above will produce a page with a single line of text (contained in the `<p></p>` element).

**Attributes** can be used to add extra information to elements. In the above example, we have set the `lang` attribute to `"en-us"`. Many attributes are element specific, with predetermined values.

To see the code behind a web page, you can usually right click the page and select **view source**.

### Extra Markup

**Doctypes** specify which version of HTML a browser should use to render a page. Generally browsers will default to HTML 5, but it is good practice to include the `<!DOCTYPE html>` element at the beginning of your web page

**Comments** in HTML are added using the `<!--  -->` tags. Adding comments to your code is good practice so that anyone can understand what's going on. Comments can also be used to temperarily disable sections of code.

**ID Attribute** is used to assign a unique identifier to an element. ID attribute content should start with a letter or underscore(_). The ID element is a **global attribute** because it can be used in any element.

**Class Attribute** is another global attribute. It can be used to group elements together. The class attribute doesn't directly affect the appearance of content, but classes can be styled altogether using CSS.

`<div>` elements can be used to group content together in a block. The div element can also be used for orgainzation of content, to separate sections of your page. This can make reading your code easier as well.

`<span>` elements are similar to divs, but used inline. They usually include a class or id, and are used to style specific lines of text inside content.

`<iframe>` elements act as a window inside your webpage. The can be used to conveniently embed content into a controlled space.

### HTML5 Layout

HTML5 entroduced several new elements and features that were previously arranged and managed using the `<div>` element.

- `<header>` `<footer>` - elements made to contain content at the top or bottom of a page or containing element.
- `<nav>` - element used to contain navigational blocks. Also used occasionally to contain links at bottom of page, but this not a widely adaopted use.
- `<article>` - used to contain a section of a page that can stand on its own. A good example would be an article preview. An article element can contain its own `<header>` and `footer` elements.
- `<aside>` - used inside an article to contain information related to the article. Used outside an article to contain information related to the entire page (recent posts, search bar, chat, etc.).
- `<section>` - used to group elements together. Not to be used as a wrapper for entire page. *Everything doesn't have to be a secion but they good for dividing up a page or area*
- `<hgroup>` - used to combine multiple headings into a single heading. Can allow for item specific subheadings. Mostly used for styling purposes.
- `<figure>` `<figcaption>` - Used contain content that is not a direct part of the page's main flow. Not limited to images.
- `<a>` attribute and block elements - HTML5 allows for the `<a>` tag to be used around elements besides text, such as the `<article>` element.

For a webpage example using these new tools, refer to this htmlandcssbook.com (reference website)[http://www.htmlandcssbook.com/code-samples/chapter-17/example-with-links.html]

Older browsers will treat the new elements as in-line elements, so certain workarounds are necessary using CSS and JavaScript.

### Process and Design

When designing a website, it's good to have steps you can follow from idea to execution. When deciding your process consider the following:

- **WHO: Target Audience** - Who is your site for? Consider who your site will be aimed for. How can you reach them effectively?
- **WHAT: Meeting Needs of Visitors** - What are people going to visit your site to do, and how can you help them do it?
- **HOW OFTEN: Frequency of visitors** - Will your site benefit from frequent updates? Are there features that a visitor may use more often than others?

After deciding on content, consider organization and flow. How will you organize navigation around your site? A **site map** can be a useful visual tool for organizing site navigation, and will usually start with a home page.

Once you have an idea of navigation, **wireframes** can be used for a rough sketch of how your site will appear in a browser. Use this to consider what designs you can implement using the tools at your disposal.

Using tools like effective contrasting and grouping of information, aim to have the clearest communication possible to the user. Aim to make content easily accessible and clear to the user.

## JavaScript

### Introduction

JavaScript is a tool used to accomplish many things on a webpage. It can be used to **access** or **modify** page content, **program** rules for a browser to follow, or **react** to events such as user input.

Javascript isn't universally backwards compatible, so be mindful of older browsers if you expect your page to interact with them.

### The ABC of Programming

#### A: What is script and how do I create one?

A **script** is simply a series of instructions for a computer.

When starting to write a script, start with a large idea and gradually break things down into steps. Tools like flowcharts can be useful at a high level to visualize what inputs and outputs need to be accepted or returned to achieve your goal.

After identifying the steps of process, begin to write code to accomplish each step. **Take a granular approach**. Try to think like a computer and imagine the steps of a process as happening from top to bottom, in order. Thinking in precise steps can also be called thinking **programatically**.

#### B: How do computers fit in with the world around them?

Computers use data to create models. A computer sees a webpage as an **object**. The object contains **properties** that define characteristics and content, **methods** that perform a task associated with the page, and can respond to **events** such as user input.

These chracteristics define most interactions we have with computers. A computer recieved an HTML file containing several objects, and uses the information it is given to **model** the webpage within it's rendering engine.

#### C: How do I write a script for a web page?

While HTML and CSS determine the content and style of webpage, respectively, JavaScript determines the **behavior**.

Scripts can be placed directly into HTML using the `<script>` element, but can also be sourced from an external file using the `src=` attribute within `<scritp>`. When a broser incounters the element it will stop, load the script, and check to see if it needs to do anything.

```js
document.write('Good afternoon!');
```

Will write "Good afternoon!" to the document element of the assciated HTML page when the script is executed.

Sources:
HTML & CSS, by Jon Duckett
JavaScript & JQuery, by Jon Duckett
Associated Site: (htmlandcssbook.com))[http://www.htmlandcssbook.com/]