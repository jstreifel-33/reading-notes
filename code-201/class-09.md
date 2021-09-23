# Forms and JS Events

## Forms

Forms allow a user to interact with your webpage in some way or another. They can allow the user to add text, make choices, and submit items to your website.

### Form Structure (HTML)

* `<form>` - contains various form controls. This is the foundation of creating a form.
  * `action=" "` - required for every form. It's value is the URL of the page that will receive the submitted information.
  * `method=" "` - can be set to `get` or `post`.
    * `method="get"` - adds values to the end of the `action` URL to direct a user or retrieve information.
    * `method="post"` - sends the values in HTTP headers. `post` should be used when a file is uploaded or a submission is very long, contains sensitive data, or adds/deletes information in a database.
  * `id` - including an id attribute is important for identifying the form in JS. **Each form should be unique.**
* `<input />` - creates several different controls. The kind of control is determined by the `type=" "` attribute.
  * `type="text"` - creates a single line text input. Size should be determined through CSS.
  * `type="password"` - is identical to `"text"` but characters are blocked out to protect sensitive data.
  * `type="radio"` - allows user to pick one of a number of choices (bullet button). Cannot be deselected.
  * `type="checkbox"` - allows selection/deselection of multiple choices.
  * `type="file"` - allows selection of a file for submission. Will be followed by **Browse** button.
  * `type="submit"` - used to send a form to the server.
  * `name=" "` - assigns a label to the user input, allowing the server to identify it.
* `<textarea>` - creates a multi-line text input. Text inside this element appears in the box when the page loads.
* `<select>` - creates a drop down list. Contains 2 or more `<option>` elements
  * `<option>` - specifies options for the user. `selected="selected"` picks a default upon page load.
  * `size="number"` - makes a `<select>` element into a displayed list for the user to scroll through and make a selection.
* `<fieldset>` - groups related controls together.
  * `<legend>` - comes directly after fieldset and identifies the group.

## Lists, Tables, and Forms (CSS)

CSS has unique properties for styling lists, tables and forms.

### Styling Lists

* `list-style-type` - controls the shape or style of markers in ordered and unordered lists.
* `list-style-image` - specifies an image to be used as list markers.
* `list-style-position` - changes how wrapped text behaves for lists, matching the indent of the top line or the marker.
* `list-style` - shorthand for specifying type, image, and position in one line.

### Styling Tables

* `empty-cells` - determines if empty cells are shown or hidden. can be set to inherit parent table.
* `border-spacing``border-collapse` - controls space between cells and what happens when cells' borders meet.

### Styling Forms

Forms and form inputs obey the same rules as other elements and can be styled similarly.

* `cursor` - controls the type of mouse cursor that appears when a user does something. Custom cursors can be imported using a URL.

## Events

Events are used to trigger a function or script. When triggering a function, do not include parentheses.

The JS Event object includes many different event to track and they can be implemented in one of two ways:

```js
//Event handlers can only trigger one function:
element.onevent = functionName;

//Event listeners are more complex but can deal with multiple functions:
element.addEventListener('event', functionName, Boolean);

//Passing arguments to an event handler or listener requires a workaround using an anonymous function
element.addEventListener('event', function() {functionName(arg)}, Boolean);
```
