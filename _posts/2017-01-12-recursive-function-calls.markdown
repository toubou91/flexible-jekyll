---
layout: post
title:  "How to call a JavaScript function recursively"
date:   2017-01-12 21:00 +0200
comments: true
categories: [til, javascript]
img: js-1.png
---
<h1>Situation</h1>
So I have developed [math.js](https://www.npmjs.com/package/math.js), a small npm-package (still WIP), which contains very simple functions, in a format like below:

```javascript
greatestCommonDivisor: function (x, y) {
    var remainder = x % y;
    if (remainder === 0) {
        return y;
    }

    return greatestCommonDivisor(y, remainder);
}
```

Running the tests after having added the fore-mentioned function, wasn't as fun as I thought, though:
![Tests failed]({{ site.url }}/assets/failure.png){: .center-image }

<h1>Solution</h1>
Hopefully, js already provides a feature with the help of which we can work around situations where we need to reference the function inside itself, so, <b>we need to somehow provide a naming to the function itself</b>. This is called a <b>[named function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/name)</b>:

```javascript
 greatestCommonDivisor: function gcd(x, y) {
    var remainder = x % y;
    if (remainder === 0) {
        return y;
    }

    return gcd(y, remainder);
}
```   

Tadaaam! Tests turned green again, after this slight change.
Let's commit!

<h4>Closing Quote</h4>
> You already know where you're good at, but how sure could you be about things you never tried before?
