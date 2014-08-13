amd-window
==========

Helps depending on the **window** object

### Usage with [curl.js](https://github.com/cujojs/curl)

Your AMD module should depend on AMD window:

```js
// Uses AMD or browser globals to create a jQuery plugin.
(function (factory) {
    if (typeof define === 'function' && define.amd) {
        // AMD. Register as an anonymous module.
        define(['jquery', 'amd-window'], factory);
    } else {
        // Browser globals
        factory(jQuery, window);
    }
}(function ($, window, undefined) {
...
}));
```

### Why `window` and `undefined`?

You can read about it in this [SO question](http://stackoverflow.com/questions/8275658/passing-window-and-undefined-to-an-immediately-invoked-anonymous-function-why)

### The `window` object cannot be shadowed

```js
window = {
    num: 5,
    str: 'text'
}

if (typeof window.num === 'undefined') {
    console.log('Yes, you cannot shadow the windows object');
}
```
