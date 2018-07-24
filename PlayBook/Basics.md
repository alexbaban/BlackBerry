# PlayBook Development Basics

## Recognizing readiness

### The load event

(https://developer.mozilla.org/en-US/docs/Web/Events/load)

> The load event is fired when a resource and its dependent resources have finished loading.

``` js
window.addEventListener("load", function (e) {
    console.log("All `window` resources finished loading!");
    console.log(e);
}, false);

```

or

``` js
window.onload = function (e) {
    // statements to be executed
    console.log(e);
}

```

or 

```js
// alternative to load event
document.onreadystatechange = function () {
  if (document.readyState === "complete") {
    initApplication();
  }
}
```

or

```
document.addEventListener('readystatechange', event => {
  if (event.target.readyState === "interactive") {
    initLoader();
  }
  else if (event.target.readyState === "complete") {
    initApp();
  }
});
```

### The DOMContentLoaded event

(https://developer.mozilla.org/en-US/docs/Web/Events/DOMContentLoaded)

> The DOMContentLoaded event is fired when the initial HTML document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading. A very different event load should be used only to detect a fully-loaded page. It is an incredibly popular mistake to use load where DOMContentLoaded would be much more appropriate.

```js
document.addEventListener('DOMContentLoaded', function(e) {
    console.log('DOMContentLoaded event fired.');
    console.log(e);
});

```

## Listen for swipe down from the top bezel 

``` js
blackberry.app.event.onSwipeDown(function () {
    // reload page on swipe down
    location.reload();
});

```

## Listen for online/offline
``` js
window.addEventListener("offline", function () {
    alert("offline")
}, false);

window.addEventListener("online", function () {
    alert("online")
}, false);

```

## Check if online
``` js
window.onload = function () {
    // statements to be executed
    var isOnline = ('blackberry' in window) ? blackberry.system.hasDataCoverage() : window.navigator.onLine;
    alert("Online: " + isOnline);
}

```

## Load external JS and CSS in order using head.js 

### folder structure
```
\app\
\app\head.js
\app\jquery.min.js
\app\main.html
\app\main.js
\app\styles.css

```

### head.js
``` js
// head.js

// App.RESOLVE_LOCAL_PATH = true;

// reload page on swipe down
blackberry.app.event.onSwipeDown(function () {
    location.reload();
});

// load external JS and CSS
document.write('<script src="' + App.ROOT_DIR_PATH + '\/app\/jquery.min.js"><\/script>');
document.write('<link rel="stylesheet" type="text/css" href="' + App.ROOT_DIR_PATH + '\/app\/styles.css">');

```
