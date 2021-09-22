# CSS Styling Revisited

`float` can be used to place elements side by side, with clever use of the width property.

```css
/* From the Duckett pg 371: */
body {
  width:750px;
}
p{
  width:230px;
  float:left;
  margin:5px;
  padding:5px;
}
```

By setting the total element width (width+margin+padding) to 1/3rd of the containing body width, elements can be made to tile in columns of 3 when set to float. This method can generally be used to control how a layout looks inside of a container. Element widths can also be offset from each other to create one larger column (640 px + 320px = 960px)

## Page Size

To account for screen sizes and various resolutions, web developers generally make their pages around **960 - 1000 px wide**. This can prevent your webpage from needing to be scrolled sideways, and allow for some margin on the left/right to be clipped by the viewport.

Designers also try to convey what their site is about within the top **570 - 600 px** of a webpage, since this generally is what will be displayed to a user first before they scroll down.

## Layouts

There are two schools of thought when picking a website layout:

**Fixed Layouts** do not change size as a user increases or decreases the size of their browser window. Dimensions are usually specified in `px`. **Advantages** are more control over content placement/appearance and predictability of how your site will behave. **Disadvantages** are that you may end up with large gaps and high resolution displays or large fonts may negatively affect your ability to display content.

**Liquid Layouts** stretch and contract with the user's window. Dimensions are usually specified in `%`. **Advantages** the ability to fill a large window and adapt to different font sizes. **Disadvantages** are less control over the look of content, and the chance that lines of text may become very long and harder to read.

## CSS Frameworks

CSS frameworks are tools used to provide code for common tasks. They can be included in projects instead of writing CSS from scratch. One such framework is the **960 Grid System** available at [www.960.gs](www.960.gs).

The 960.GS framework requires that we assign specific classes to html in order to apply the rules from the premade stylesheet.

Our own style sheet will still require us to choose colors, font style, content height, padding (top/bottom), and how we want to display content within our containers that now on a grid.

## Multiple Style Sheets

Multiple style sheets can be used on the same html page.

To accomplish this through **HTML** we can use multiple `<link>` elements to call multiple style sheets. Remember that styles cascade and are applied in the order they are called.

To do the same through **CSS** we can use `@import url("other_style.css)`. It is good practice to do this at the top of your style sheet, so that it is clear immediately what is being imported. Cascading rules still apply.
