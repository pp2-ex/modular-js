JS: Best Practices
==========

A small talk about modular JS, NPM and Browserify for the Protein Prediction 2 Exercise 

Live Coding Script
==========

# It's all about the Package.json

Create first a empty folder and inside do:

```
npm init
```

This will create a package.json which essentially marks your folder as npm module

# 

In the following, we will use @anvakas looker-on module as quick demo how to include a component

With [npm](https://npmjs.org) do:

```
npm install looker-on
```

Then create an instance of looker and attach it to dom:

```js
// your index.js file
var Looker = require('looker-on');
new Looker(document.body);
```

``` html
<!DOCTYPE html>
<html lang="en">

<head>
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <script src='bundle.js'></script>
</body>

</html>
```

`style.css` and `bundle.js` are produced by [parcelify](https://www.npmjs.org/package/parcelify) and [browserify](http://browserify.org/):

```
parcelify index.js -c style.css
browserify index.js > bundle.js
```

Now you can open `index.html` and observe two eyes observing you.
We will adjust the `style.css` for our needs.

# Events

You can make these eyes track position of the mouse cursor by changing `index.js` to

``` js
// your index.js file
var Looker = require('looker-on');
var observer = new Looker(document.body);
document.body.addEventListener('mousemove', function (e) {
  observer.lookAt(e.clientX, e.clientY);
}, false);

```

# BioJS Slush

We developed biojs slush to quickly generate a professional dev enviroment for you. Just 

```
npm install slush-biojs
```

and then do in an empty folder 

```
slush biojs
```

Welcome to the World of BioJS!



