# CSS Transforms, Transitions and Animations

## Transforms

Source: [shayhowe HTML/CSS Lesson 7](https://learn.shayhowe.com/advanced-html-css/css-transforms/)

CSS3 introduced the `transform` property, which allows us to change the shape of elements in either 2d or 3d. The syntax is simply `transform: value`.

### 2D transforms

2d transforms work on the x and y axes of the page, and include the following:

* `rotate(degrees)` - rotates an element by the specified amount of degrees. Positive numbers are clockwise, while negative are anti-clockwise.
* `scale(number)` - default scale is 1, changes the apparent size of an element in relation to its original size.
* `translate(x,y)` - works similarly to relative positioning. Moves an element the specified x and y amount.
* `skew(degrees)` - distorts elements on the horizontal or vertical axis, or both.

### 3D transforms

3D transforms are used to alter elements on 3 axes, and include:

* `rotate(degrees)` - rotates an element, in 3 dimensions. Can specify x, y, or z axis.
* `scale(number)` - same thing but includes the z axis. May require rotating object to see z-axis changes.
* `translateZ(amount)` - moves elements "up and down" on the z-axis, appearning above and below the page to scale.

## Transitions and Animations

Source: [shayhowe HTML/CSS Lesson 8](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)

### Transitions

For a transition to take place, an element must have a change in state, such as `:hover` `:focus` `:active` etc. The property to be transitioned should be specified using `transition-property`.

`transition-duration` and `transition-timing-function` affect the speed of the transition.

`transition-delay` can be used to add a delay to a transition.

### Animations

Animations are created using the `@keyframes` rule in CSS.

```CSS
/* example from source:*/
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
```

By using `animatio-name` and `animation-duration` properties, we can add animations that we define using `@keyframes` to an element. The keyframes act as points within the provided duration, up to 100%. The same animation can be used with multiple durations, but will appear to be faster or slower depending on how much time the animation is given to complete.
