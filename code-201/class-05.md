# Images, Colors, and Text

## Images (HTML)

### Including Images in a Website

It's good practice to place your website images in a folder made for that purpose. They are added to your HTML using the `<img />` element, which includes the following attributes:

* `src` - specifies the path to the image you wish to display. Can be relative or absolute.
* `alt` - provides a text description which is used to describe the image if you cannot see it.
* `title` - provides additional information what will be displayed when a user mouses over the image.
* `height` - specifies the height of the image in pixels.
* `width` - specifies the width of the image in pixels.

Aligning images should be accomplished with CSS but, the `align` attribute was once commonly used to indicate how other content should be organized around an image. This is now more commonly accomplished using the `display:` CSS property.

It is helpful to know which image format is best for saving images:

* JPEG - Best used for images that contain a lot of different colors.
* PNG - Best used for images with few colors or large areas of the same color. Also used for images that include areas of transparency.
* GIF - Used for animated images. Generally follows the same rules as PNG (there are static GIFs), but usually animated.

### HTML5 Figures

The `<figure>` and `<figcaption>` elements can be used to render images with a caption below them.

The `<figure>` element acts as the parent to an `<img>` and `<figcaption>`, allowing them to be grouped together. Before HTML5 there was no way to directly associate an image with its caption.

## Colors (CSS)

Colors are what gives a page its personality and there are many tools we can use to apply colors to a web page:

`color:` - applies a color to the text of an element. Can accept RGB, Hex, RGBA (CSS3), HSL(CSS3), or one of 147 predefined color names.
`background-color:` - Changes the background color of an element. Not specifying a background color will set a background to transparent. Accepts the same values the `color` property.
`opacity:` - a number between 0.0 and 1.0 used to define how opaque and element is. 0.0 is transparent, 1.0 is fully opaque.

It's important to consider contrast when defining colors for a website. High or medium contrast text is easier for humans to read, and medium contrast or light text on a dark background benefits from spaced out font for ease of reading.

## Text

There are generally 3 different typefaces:

* **Serif** - Serif fonts have extra details on the ends of main strokes. The details are referred to as "serifs."
* **Sans-Serif** - these fonts have straight ens to letters and therefore have a cleaner design.
* **Monospace** - All characters are the same width. Commonly used in code because the align better.

CSS allows us to change the font to fit our needs:

* `font-family:` - Allows you to specify a font to use, and multiple fonts can be listed, separated by commas. The browser will the first one installed on the user's computer.
* `font-size:` - Specifies the size of font. Can accept pixels, percentages, and ems.
* `@font-face {}` - Allows you to specify a font that may not be on a user's computer, but providing a path within your site the font.
  * `font-family:` - The name of the font you are specifying. Will be used to implement the font.
  * `src:` - The path to the font.
  * `format:` - Specifies the format the font is supplied in.
* `font-weight:` - Can be used to bold text. Accepts `normal` and `bold` as values.
* `font-style:` - Used to create italic text. Accepts `normal` `italic` and `oblique` values.
* `text-transform:` - Changes the case of text.
* `text-decoration:` - Applies decoration. Values: `none`, `overline`, `line-through`, `blink`
* `line-height:` - Specifies how much space should be between the bottom of one line of the text and the bottom of the next. Useful for spacing paragraphs.
* `letter-spacing:`, `word-spacing:` - Specifies space between words or letters. Typefaces typically use 0.25em as the default space between words, so if letter-spacing is increased consider increasing word-spacing for readability.
* `text-align:` - controls text alignment. Accepts `left`, `right`, `center`, and `justify`.
* `vertical-align:` - determines how text aligns with other in-line elements.

Links can be styled using the `:link` and `:visited` pseudo-classes. These allow us to control how a link looks before and after it has been visited by a user.

There are other pseudo-classes that can be used to provide a feeling of interactivity to the user:

* `:hover` - changes the style of an element when the user places their mouse of it.
* `:active` - changes the style of an element when activated by the user. This can be used to make buttons feel like they're being pushed by using subtle style changes.
* `:focus` - applied when an element is focused by the user.

NOTE: when pseudo-classes are used they should be in this order: `:link`, `:visited`, `:hover`, `:focus`, `:active`
