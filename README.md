# JavaScript Easy Color Parser for Node JS
### Converts colors to formats hex, rgb, rgba, hsl, hsla and cmyk.

[![Build Status](https://travis-ci.org/salomaosnff/easy-color-parser.svg?branch=master)](https://travis-ci.org/salomaosnff/easy-color-parser)
[![downloads](https://img.shields.io/npm/dm/easy-color.svg)](https://www.npmjs.com/package/easy-color)
---
Fork of [Adrian's](https://github.com/adrianbrs) [project](https://adrianbrs.github.io/easy-color-parser)

---

### Supported color formats
* HEX
* SHORT HEX
* RGB
* RGBA
* HSL
* HSLA
* CMYK

---

### Installation
```bash
npm install easy-color
```

### How to use
Import the module and create an instance of the constructor by placing the color you want to convert <br />
You can put in any supported format <br />
Example:
```js
var Color = require('easy-color');
// Instance
var parser = new Color("#00AAFF"); // You can also add: # 0af, rgb (0, 170, 255), hsl (..., etc ...

// Converta
parser.toHEX();  // Converts to HEX format   (Hexadecimal)
parser.toRGB();  // Converts to RGB format  (Red, Green, Blue)
parser.toRGBA(); // Converts to RGBA format (Red, Green, Blue, Alpha)
parser.toHSL();  // Converts to HSL format  (Hue, Saturation, Lightness)
parser.toHSLA(); // Converts to HSLA format (Hue, Saturation, Lightness, Alpha)
parser.toCMYK(); // Converts to CMYK format (Cyan, Magenta, Yellow, Key)
```
To convert the values of a color separately use:
```js
// RGB
var parser = new Color.fromRGB(0, 170, 255); // Values
var parser = new Color.fromRGB([0, 170, 255]); // Array of values
var parser = new Color.fromRGB({ r: 0, g: 170, b: 255 }); // Object of values

// RGBA
var parser = new Color.fromRGBA(0, 170, 255, 1); // Values
var parser = new Color.fromRGBA([0, 170, 255, 1]); // Array of values
var parser = new Color.fromRGBA({ r: 0, g: 170, b: 255, a: 1 }); // Object of values

// HSL
var parser = new Color.fromHSL(200, 100, 50); // Values
var parser = new Color.fromHSL([200, 100, 50]); // Array of values
var parser = new Color.fromHSL({ h: 200, s: 100, l: 50 }); // Object of values

// HSLA
var parser = new Color.fromHSLA(200, 100, 50, 1); // Values
var parser = new Color.fromHSLA([200, 100, 50, 1]); // Array of values
var parser = new Color.fromHSLA({ h: 200, s: 100, l: 50, a: 1 }); // Object of values

// CMYK
var parser = new Color.fromCMYK(100, 33, 0, 0); // Values
var parser = new Color.fromCMYK([100, 33, 0, 0]); // Array of values
var parser = new Color.fromCMYK({ c: 100, m: 33, y: 0, k: 0 }); // Object of values
```
--
You can also get the name of the color format that you have set to make it easier in some cases
```js
parser.colorType(); // Returns the color format defined
```
--
So you can also convert a color to a format from the format name
```js
parser.to("RGBA") // In this case it will return the color value in RGBA format, eg rgba (0, 170, 255, 1)
```
--

### CSS Color Table
You can pick up the CSS color table used to convert the color name to HEX, eg: white -> #FFFFFF <br />
Read about <a href="http://www.w3schools.com/cssref/css_colors.asp" target="_blank">CSS Color Table</a> <br />
To get the array of this table use:
```js
var table = parser.CSSColorTable;
```
With this table you can convert colors just by name too <br />
For example:
```js
var parser = new EasyColorParser("aqua"); // Creates the instance from the css color name
parser.toHex(); // #00FFFF
```
--
### Values
To get the separate values for each format use:
```js
var rgb = parser.rgb,     // Returns an array with the RGB values  ->  {r:Number, g:Number, b:Number}
    hsl = parser.hsl,     // Returns an array with the HSL valuesL ->  {h:Number, s:Number, l:Number}
    cmyk = parser.cmyk,   // Returns an array with the CMYK values ->  ...
    alpha = parser.alpha; // Returns color transparency            ->  1

// RGB
var red = rgb.r;
var green = rgb.g;
var blue = rgb.b;

// HSL
var hue = hsl.h;
var saturation = hsl.s;
var lightness = hsl.l;

// CMYK
var cyan = cmyk.c;
var magenta = cmyk.m;
var yellow = cmyk.y;
var key = cmyk.k;
```

## Links
- [Easy Color for browser](https://adrianbrs.github.io/easy-color-parser)
- [Send a Pull Request](https://github.com/salomaosnff/easy-color-parser/pulls)
- [My Github](https://gitbuh.com/salomaosnff)
