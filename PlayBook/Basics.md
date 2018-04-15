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

## Load JavaScript libs in order using app.js 

### folder structure
``` html
- \css
- \js
    - app.js
- jquery.min.js
- main.html
- main.js
- some.library.js

```

### app.js
``` js
// enable loading of local images
var resolveImagesPath = "true";

// load JavaScript libs
;(function () {
    var cameraPath = blackberry.io.dir.appDirs.shared.camera.path;
    var sharedPath = blackberry.io.dir.getParentDirectory(cameraPath);
    var appFolderName = blackberry.app.name.toLowerCase().replace(/\s+/g, "");
    var appPath = sharedPath + "/documents/" + appFolderName;
    document.write('<' + 'script src="' + appPath + '\/jquery.min.js' + '" type="text\/javascript"><' + '\/script>');
    document.write('<' + 'script src="' + appPath + '\/coin-slider.min.js' + '" type="text\/javascript"><' + '\/script>');
})();


```
