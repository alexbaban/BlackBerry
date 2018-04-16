# React on Playbook tablet (starter)

> Version 16... does not work   
> Version 15.6.2 works, download link: (https://github.com/facebook/react/releases/tag/v15.6.2)

## File structure (using a "Pod", \documents\pod[number])
```
css\
js\
js\head.js
main.html
main.js
react-dom.min.js
react.min.js

```

## head.js
``` js
// head.js

blackberry.app.event.onSwipeDown(function () {
    // reload page on swipe down
    location.reload();
});

// load JavaScript libs
;(function () {
    var cameraPath = blackberry.io.dir.appDirs.shared.camera.path;
    var sharedPath = blackberry.io.dir.getParentDirectory(cameraPath);
    var appFolderName = blackberry.app.name.toLowerCase().replace(/\s+/g, "");
    var appPath = sharedPath + "/documents/" + appFolderName;
    document.write('<script src="' + appPath + '\/react.min.js' + '"><\/script>');
    document.write('<script src="' + appPath + '\/react-dom.min.js' + '"><\/script>');
})();

```

## main.html
``` html
<!-- // main.html -->

<div id="app"></div>

```

## app.js
``` js
// main.js

ReactDOM.render(
    React.DOM.h1(null, 'Hello, World!'),
    document.getElementById('app')
);

```
