# Test App with ES6 and Babel

> This is a test app with ECMAScript 6, using Babel (in browser transpiling). This will force the browser to convert ES6 to ES5 at run time. It's expected that the app will run much slower.

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
    
    // default function parameters example
    var nameBuilder = function (
        firstName = "John", 
        lastName = "Doe"
    ) { 
        console.log(firstName + " " + lastName); 
    };

    nameBuilder();

</script>

```

## main.js
``` js
// main.js (empty)

```

## Result
When the app is launched or on page refresh, `John Doe` shows in console. As expected the app runs very slow.

## More examples

### the keyword `let`

``` html
<!-- // main.html -->

<script type="text/babel">
    
    var x = 10;

    if (x) {
        let x = 4;
    }

    console.log(x); 
    // shows `10`

</script>

```

### template strings `${variable}`
``` html
<!-- // main.html -->

<script type="text/babel">
    
    function print (firstName) {
        console.log(`Hello ${firstName}`);
    }

    print("Alexandru"); 
    // shows `Hello Alexandru`

</script>

```

### the spread operator `...`
``` html
<!-- // main.html -->

<script type="text/babel">
    
    var cats = ["Tabby", "Siamese", "Persian"];
    var dogs = ["Golden Retriever", "Pug", "Schnauzer"];
    
    var animals = ["Whale", "Giraffe", ...cats, "Snake", ...dogs, "Coyote"];

    console.log(animals);
    // shows `["Whale", "Giraffe", "Tabby", "Siamese", "Persian", "Snake", "Golden Retriever", "Pug", "Schnauzer", "Coyote"]`

</script>

```

### arrow functions `=>`
``` html
<!-- // main.html -->

<script type="text/babel">
    
    var studentList = (students) => console.log(students);
    
    studentList(["Joe", "Cindy", "Jeanne"]); 
    // shows `["Joe", "Cindy", "Jeanne"]`

</script>


```
