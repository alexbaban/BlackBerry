# BlackBerry PlayBook

## WebWorks

### user agent
`navigator.userAgent` returns:
   
`"Mozilla/5.0 (PlayBook; U; RIM Tablet OS 2.1.0; en-US) AppleWebKit/536.2+ (KHTML, like Gecko) Version/7.2.1.0 Safari/536.2+"`

### css gradient
from this:

(https://css-tricks.com/css3-gradients/)

```css
  /* Safari 4, Chrome 1-9, iOS 3.2-4.3, Android 2.1-3.0 */
  background-image:
    -webkit-gradient(linear, left top, right top, from(red), to(#f06d06));
  
  /* Safari 5.1, iOS 5.0-6.1, Chrome 10-25, Android 4.0-4.3 */
  background-image:
    -webkit-linear-gradient(left, red, #f06d06);

  /* Opera 15+, Chrome 25+, IE 10+, Firefox 16+, Safari 6.1+, iOS 7+, Android 4.4+ */
  background-image:
    linear-gradient(to right, red, #f06d06);

```

the one that works is:
```css
 
  /* Safari 5.1, iOS 5.0-6.1, Chrome 10-25, Android 4.0-4.3 */
  background-image:
    -webkit-linear-gradient(left, red, #f06d06);

```
