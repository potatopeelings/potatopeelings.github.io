---
layout: post
title: Functions and Shorter Code
---

Brevity is a bad measure of maintainability. 

Yes, maintainable code is usually shorter. But making the code as short as possible doesn't mean maximum maintainability.

And we're not talking about cases where the shortest version is some one liner with obscure operators or side-effects and single character variables. We're talking about run-of-the-mill replacing repeated blocks of code with a function definition and function calls. 

Functions improve maintainability - the key is figuring out what goes into a function and what stays out of it.

A quick example

```javascript
var a = b / 1000;
var c = d / 1000;
```
Going into auto-pilot and converting this into a function, gets us
```javascript
var a = fn(b);
var c = fn(d);

function fn(x) {
    return x / 1000;
}
```
But then someone hands us the commented, nicely named version of the snippet.

```javascript
// convert to meters
var m = mm / 1000;
// convert to kilograms
var kg = gm / 1000;
```

If you have to step into the function while debugging, your function boundary is mostly wrong.
