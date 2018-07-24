# Keyframe Animation

## App Structure

```
\app
    \main.html
    \head.js
    \main.js
    \styles.css
```

### main.html

```html
<!-- // main.html -->

<div class="box"></div>
```

### head.js

```js
// head.js

blackberry.app.event.onSwipeDown(function () {
    // reload page on swipe down
    location.reload();
});

document.write('<link rel="stylesheet" type="text/css" href="' + App.ROOT_DIR_PATH + '\/app\/styles.css">');
```

### main.js

```js
// main.js

document.onreadystatechange = function () {
    console.log(document.readyState);

}

window.onload = function (event) {

    console.log(event.type);

    var aBox = document.querySelector('.box');

    aBox.addEventListener('touchstart', function (event) {
        aBox.setAttribute('class', 'box--animated')
        aBox.addEventListener("webkitAnimationEnd", customFunction);
        console.log(event);
    });

    function customFunction(event) {
        aBox.removeEventListener("webkitAnimationEnd", customFunction);
        event.target.setAttribute('class', 'box');
        console.log(event);
    }

}
```

### styles.css

```css
body {
    background-color: #868e96;
}

@-webkit-keyframes over-and-back {
    0% {
        background-color: hsl(0, 50%, 50%);
        -webkit-transform: translate(0);
    }

    50% {
        -webkit-transform: translate(924px);
    }

    100% {
        background-color: hsl(270, 50%, 90%);
        -webkit-transform: translate(0);
    }
}

.box {
    width: 100px;
    height: 100px;
    background-color: green;
}

.box--animated {
    width: 100px;
    height: 100px;
    -webkit-animation: over-and-back 1.5s linear 3;
}

```
