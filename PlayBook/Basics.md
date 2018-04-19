# PlayBook Development Basics

## Recognizing readiness

``` js

window.addEventListener("load", function () {
    //statements to be executed
}, false);

```

or

``` js
window.onload = function (evt) {
    // statements to be executed
    console.log(evt);
}

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
