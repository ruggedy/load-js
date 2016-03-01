# load-js
Promise based script loader for the browser using async script tags.

This is a UMD module, so feel free to include it in your nodejs bundling pipeline or directly in the browser via script tags.

> Promise implementation needs to be polyfilled if environment does not already provide it.

## Install

```
$ npm install load-js
```

## Usage

Let's just give a simple example where `load-js` is loaded via a script tag in you HTML

``` html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

    <!-- polyfill promise if needed -->
    <script type="text/javascript" src="node_modules/spromise/dist/spromise.min.js"></script>
    <script>if (typeof(window) !== 'undefined' && !window.hasOwnProperty("Promise")) window.Promise = spromise;</script>

    <!-- Include load-js -->
    <script type="text/javascript" src="node_modules/load-js/index.js"></script>

    <script type="text/javascript">
      <!-- load your stuff -->
      loadJS("https://code.jquery.com/jquery-2.2.1.js")
        .then(function() {
          console.log("jQuery is loaded");
        });
    </script>
  </head>

  <body>
  </body>
</html>
```
