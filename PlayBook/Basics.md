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


