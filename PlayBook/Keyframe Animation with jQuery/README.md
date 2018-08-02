# Keyframe Animation with jQuery

## App structure
```
app\
   \head.js
   \main.html
   \main.js
   \styles.css
   \jquery.min.js
   \license.txt
```

## head.js
```js
// head.js

blackberry.app.event.onSwipeDown(function () {
    // reload page on swipe down
    location.reload();
});

document.write('<link rel="stylesheet" type="text/css" href="' + App.ROOT_DIR_PATH + '\/app\/styles.css">');
document.write('<' + 'script src="' + App.ROOT_DIR_PATH + '\/app\/jquery.min.js' + '"><' + '\/script>');

```

## main.html
```html
<!-- // main.html -->

<div id="container"></div>

```

## styles.css
```css
/* styles.css */

body {
    background-color: whitesmoke;
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

p {
    text-align: center;
    font-size: 95px;    
    color: lightgreen;
    display: inline;
}

.box {
    width: 100px;
    height: 100px;
    background-color: green;
    margin-top: 15px;
    margin-bottom: 15px;
}

.box--animated {
    width: 100px;
    height: 100px;
    margin-top: 15px;
    margin-bottom: 15px;
    -webkit-animation: over-and-back 1.5s linear 3;
}

```

## main.js
```js
// main.js

document.onreadystatechange = function () {
    console.log('document: ', document.readyState);
}

window.onload = function (event) {

    console.log('window: ', event.type);

    var icons = [
        '&#x2614;', // umbrella
        '&#x2708;', // airplane
        '&#x2694;', // swords
        '&#x262F;', // yin and yang
        '&#x2615;' // coffee
    ];
    
    var container = $('#container'); // <div id="container"></div> is defined in main.html
    
    // add boxes with icons on screen
    icons.forEach(function (icon) {
        container.append('<div class="box"><p>' + icon + '</p></div>');
    });

    // when touched slide to the right edge and back (three times)
    container.children().on(
        'touchstart',
        function (event) {

            console.log(event.type);

            event.currentTarget.setAttribute('class', 'box--animated');

            $(this).one(
                'webkitAnimationEnd oanimationend msAnimationEnd animationend',
                function (event) {
                    console.log(event.type);
                    event.target.setAttribute('class', 'box');
                }
            );

        }
    );

}

```

## screenshot
<img src="https://github.com/alexbaban/BlackBerry/raw/master/PlayBook/Keyframe%20Animation%20with%20jQuery/Keyframe_Animation_with_jQuery.png" width="400" />   
   
<img src="https://github.com/alexbaban/BlackBerry/raw/master/PlayBook/Keyframe%20Animation%20with%20jQuery/Keyframe_Animation_with_jQuery_animated.png" width="400" />

