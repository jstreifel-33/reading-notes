# Local Storage

## The Before Times

Before HTML5, there wasn't a universal way to store user data. There were cookies, which could store small amounts of data but were a poor solution because they slow down a browser if used too heavily.

When browsers were still being developed and fighting for the top, they all developed their own solutions that were very browser specific.

HTML5 set out to change that.

## The Now Times

With HTML5 came "HTML5 Storage," a specification properly called [Web Storage](https://html.spec.whatwg.org/multipage/webstorage.html). It was originally a part of the HTML5 specification but later split off into its own spec.

HTML5 storage is a way for web pages to store names key/value pairs locally within the browser. They persist even after closing a window or navigating away from a page.

HTML5 storage is access through the `localStorage` object on the global `window` object.

## Using HTML5 Storage

HTML5 data is stored using key/value pairs.

**Keys** are stored as strings, and recalled using that same string.

**Values** can be any data-type and are stored as strings. This means they are also retrieved as strings and must be **parsed** to the proper data-type before use.

`setItem()` with an existing key will overwrite the value. `getItem()` on a nonexistent key will return `null`.

`localStorage` can also be used like an associative array. Square brackets can be used to retrieve values. `localStorage["name"]`

## Tracking Changes

Changes can be tracked by watching the `storage` event on the `window` object.

```js
if (window.addEventListener) {
  window.addEventListener("storage", handle_storage, false);
} else {
  window.attachEvent("onstorage", handle_storage);
};
```

The storage event object has the following properties:

* `key` - string indicating the key added, removed, or modified.
* `oldValue` - previous value or `null` if a new item was added.
* `newValue` - the new value, or `null` if an item was removed.
* `url` - the page which called a method that triggered the change.

## Competing Visions for the Future

While HTML5 storage is useful, there are still competing ideas for the future of web storage.

**Web SQL** uses a web wrapped version of SQL. This allows for database use and management from within JavaScript.

**Indexed Database API** uses an *object store*. Indexed DB uses databases with records. Each record has fields similar to an object. Each field has a datatype and is set up when the database is initialized. Indexed DB is still not widely implemented, and has only found a home in Mozilla's Firefox for now.
