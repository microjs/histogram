[![Build Status](https://secure.travis-ci.org/microjs/histogram.png?branch=master)](https://travis-ci.org/microjs/histogram)
Histogram
=========

Provides a histogram data structure from PNG, JPEG or GIF files using canvas.
This library works in nodejs and in any canvas supporting browser.

Install npm:

    npm install histogram

Install client:

    component install microjs/histogram


Example usage
-------------

NodeJS
``` javascript
var histogram = require('histogram');

histogram(fileName || Buffer, function (data) {
  console.log(filePath + ' has ' + data.colors.rgba + ' colors');
});
```

Browser with component
``` javascript
var histogram = require('histogram');
histogram(URL || FileReader.result, function (data) {
  console.log(filePath + ' has ' + data.colors.rgba + ' colors');
});
```

Data structure
--------------
``` javascript
{
    red: new Array(256), // Count of the number of times a value appears in the red channel
    green: new Array(256), // Count of the number of times a value appears in the green channel
    blue: new Array(256), // Count of the number of times a value appears in the blue channel
    alpha: new Array(256), // Count of the number of times a value appears in the alpha channel

    colors: {
        rgb: 0, // Number of unique RGB colors
        rgba: 0 // Number of unique RGBA colors
    },

    palettes: {
        rgb: [], // Array of unique colors in hex notation
        rgba: [] // Array of unique colors in hexa notation
    },

    greyscale: true, // Indicates whether all colors are greyscale or not
    alphachannel: false // Indicates that one or more pixels are translucent
}
```

License
-------
This software is licensed under the beerware license. Do whatever you want with it.
If we meet some day, and you think this stuff is worth it, you can buy me a beer in return.
