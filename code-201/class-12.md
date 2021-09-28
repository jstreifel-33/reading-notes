# Chart.js and Canvas

[MDN: Basic usage of canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)

As the name implies, chart.js is a JavaScript plugin that we can use to make charts. It takes advantage of HTML5's canvas element to do so.

Chart.js can be downloaded [here](https://github.com/chartjs/Chart.js).

A `<canvas>` element is used to render the chart, with attributes `id` `width` and `height`. The `<canvas>` element also allows for fall-back content, by placing information inside of the opening and closing tag to be displayed in the case that the chart is unable to render.

Chart.js will require JavaScript to use. The script will need to point to the `<canvas>` element and retrieve it's context (2d in the example below).

```js
//from MDN:
var canvas = document.getElementById('tutorial');
var ctx = canvas.getContext('2d');
```

[MDN: Drawing shapes with canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes)

Canvas draws on a drid, where 1 unit is normally equal to 1 pixel. The **origin** of the grid is in the top-left corner. **X** increments **right** and **Y** increments **down**.

There are functions for drawing shapes and paths, all included in the MDN reference. Whatever is drawn by the JS is shown on the canvas, provided is has enough space.

```js
//from MDN:
//Drawing a Triangle
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(75, 50);
    ctx.lineTo(100, 75);
    ctx.lineTo(100, 25);
    ctx.fill();
  }
}
```

`beginPath(x,y)` `moveTo(x,y)`, and `lineTo(x,y)` can be used to draw shapes freehand, without specific functions.

`arc(x,y,startAngle,endAngle,direction)` and `arcTo(x1,y1,x2,y2,radius)` can be used to draw circles. Angles are measured in **radians**.

[MDN: Applying Styles and Colors](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)

Canvas supports many colors and styles of lines. `fillStyle = color` sets a style for filling shapes and `strokeStyle = color` sets style for outlines.

`globalAlpha = transparencyValue` is used to set transparency of all future shapes drawn on canvas.

There are also several properties for styling lines:

 * `linewidth = value` sets the width of lines drawn
 * `lineCap = type` sets the appearance of the ends of lines
 * `lineJoin = type` sets the appearance of the "corners" where lines meet
 * `miterLimit = value` sets a limit of the miter where two lines join at a sharp angle. This lets you control how thick the junction is.
 * `getLineDash()` returns the current line dash pattern  array
 * `setLineDash(segments)` sets the line dash pattern
 * `lineDashOffset = value` Specified where to start a dash array on a line

 [MDN: Drawing Text](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)

 Canvas can render text with two methods:

 * `fillText(text, x, y [, maxWidth])` Fills a given text at the given (x,y) position. Optional max width.
 * `strokeText(text, x, y [, maxWidth])` Strokes a given text at the given (x,y) position. Optional max width.

 Fill text is filled in, while stroke text is outlines. Canvas text can be styles with properties:

 * `font = value` text style being drawn. Uses the same syntax as CSS `font`
 * `textAlign = value` can be set to `start`, `end`, `left`, `right`, or `center`. Default is start.
 * `textBaseline = value` Baseline alignment. Can be `top`, `hanging`, `middle`, `alphabetic`, `ideographic`, or `bottom`. Default is `alphabetic`.
   * MDN reference has a useful graphic illustrating these.
 * `direction = value` directionality. Can be `ltr`, `rtl`, `inherit`. Default is `inherit`.

 `measureText()` can be used to measure drawn text. It returns a "TextMetrics" object containing the width (in px) that the specified text will be when drawn.

 ```js
//from MDN:
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');
  var text = ctx.measureText('foo'); // TextMetrics object
  text.width; // 16;
}
 ```