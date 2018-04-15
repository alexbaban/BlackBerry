# Test App with ES6 and Babel

This is a test app with ECMAScript 6, using Babel (in browser transpiling). The result of the test is that, it runs, but it's very slow.

## File structure (using a "Pod", \documents\pod[number])
``` 
css\
js\
js\head.js
browser-polyfill.min.js
browser.min.js
main.html
main.js

```

## head.js
``` js
// reload page on swipe down
blackberry.app.event.onSwipeDown(function () {
    location.reload();
});

// load JavaScript libs
; (function () {
    var cameraPath = blackberry.io.dir.appDirs.shared.camera.path;
    var sharedPath = blackberry.io.dir.getParentDirectory(cameraPath);
    var appFolderName = blackberry.app.name.toLowerCase().replace(/\s+/g, "");
    var appPath = sharedPath + "/documents/" + appFolderName;
    document.write('<' + 'script src="' + appPath + '\/browser-polyfill.min.js' + '" type="text\/javascript"><' + '\/script>');
    document.write('<' + 'script src="' + appPath + '\/browser.min.js' + '" type="text\/javascript"><' + '\/script>');
})();

```

## main.html
``` html
<!-- // main.html -->

<script type="text/babel">
    
    var nameBuilder = function (
        firstName = "John", 
        lastName = "Doe"
    ) { 
        console.log(firstName + " " + lastName); 
    };

    nameBuilder();
    nameBuilder('Alex', 'Baban');

</script>

```

## main.js
``` js
// main.js (empty)

```
