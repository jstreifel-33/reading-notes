# Introductory HTML and JavaScript

## HTML

### Introduction

People access the web in a variety of different ways, including:

- Browsers: programs like Internet Explorer, Google Chrome, and Firefox. Viewing a webpage will usually require an address.
- Web Servers: special computers that are always connected to the internet. These host websites and when a browser goes to access a web page, it sends a request to a web server.
- Devices: Phones, tablets, smart tvs, laptop and desktop computers. People access the internet from a wide range of devices and it's important to keep these in mind.
- Screen Readers: programs that read the contents of a computer screen to the user. Keep accessibility in mind when designing a web page.

## Structure

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

## Extra Markup

**Doctypes** specify which version of HTML a browser should use to render a page. Generally browsers will default to HTML 5, but it is good practice to include the `<!DOCTYPE html>` element at the beginning of your web page

**Comments** in HTML are added using the `<!--  -->` tags. Adding comments to your code is good practice so that anyone can understand what's going on. Comments can also be used to temperarily disable sections of code.

**ID Attribute** is used to assign a unique identifier to an element. ID attribute content should start with a letter or underscore(_). The ID element is a **global attribute** because it can be used in any element.

**Class Attribute** is another global attribute. It can be used to group elements together. The class attribute doesn't directly affect the appearance of content, but classes can be styled altogether using CSS.

`<div>` elements can be used to group content together in a block. The div element can also be used for orgainzation of content, to separate sections of your page. This can make reading your code easier as well.

`<span>` elements are similar to divs, but used inline. They usually include a class or id, and are used to style specific lines of text inside content.

`<iframe>` elements act as a window inside your webpage. The can be used to conveniently embed content into a controlled space.

## HTML5 Layout

