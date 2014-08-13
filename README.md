amd-window
==========

Helps depending on the window object

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

