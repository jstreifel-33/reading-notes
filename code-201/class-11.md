# Audio, Video, Images

## Images

HTML Duckett Ch. 16

Images can be resized using the `width` and `height` css properties. To make things easier, consider assigning classes to common img sizes and managing layouts that way. This can help when working in a grid layout.

Alignment is most commonly achieved using the `float` property which can place images to the right or left of a page. Creating classes for this can be helpful as well. (`img.align-left` & `img.align-right`). Images can be centered using `display:block` and `margin:auto`.

`background-image` can be used to assign as image to the background of an element. There are multiple properties which can be used to modify this:

* `background-repeat` is used to repeat a background vertically and horizontally. Useful for tiled backgrounds.
  * `repeat-x` and `repeat-y` will only tile in the x or y direction, respectively.
  * `no-repeat` ensures the image is only shown once.
* `background-attachment` can be set to `fixed` or `scroll` to determine how the image behaves when the user moves the page.
* `background-position` can change where in the element an image appears if not set to repeat.

By using the background as a frame, images with multiple styles can be used and manipulated to make elements appear to change based on user action. A button may have 3 different styles of image all in one background, and use the `background-position` property to only display one at a time depending on user input by utilizing the `:hover` and `:active` CSS selectors. When an image is used this way, it is referred to as a **sprite**.

## Practical Information

HTML Duckett Ch. 19

**SEO**, or Search Engine Optimization, is the practice of trying to help your site appear near the top of relevant search results.

On-page techniques of SEO include tailoring the text of your site to include words that a potential user might search for.

Off-page techniques of SEO include getting other sites to link to your site, with relevant information included between the `<a>` tags.

Analytics can be used to learn more about visitors to your page. [Google Analytics](https://analytics.google.com/analytics/web/provision/#/provision) is a good place to start.

## Video

[MDN: Video and Audio API's](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)

Audio and Video can be added to a website by using the `<audio>` and `<video>` elements. Typical implementation looks like this:

```html
<!-- from MDN: -->

<video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
</video>

```

The `controls` attribute seen above implements a default set of playback controls. Without specifying this, there will be no controls on your media.

If you want something other than the default controls, the HTML5 spec includes an [HTMLMediaElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement) API that allows for programmatic controls. Using this you can combine, HTML, CSS, and JS to create your own unique media controls.

The listed MDN reference for this section has a full tutorial for creating controls, so reference that and their HTMLMediaElement API article (liked in previous paragraph) if you want to undertake the task of creating your own media controls.
