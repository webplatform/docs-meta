---
title: 'parseInt'
tags:
  - JavaScript
uri: 'Meta:javascript/functions/parseInt'

---
**Merge Candidate**: This page is a candidate for merge with the following pages: [[[1]](http://docs.webplatform.org/wiki/javascript/parseInt)]

When a `String` variable containing numbers is passed as an argument of the `parseInt()` function, it returns the equivalent `Integer` variable, so it can be manipulated as a number to do calculations or logic tests.

    var foo = "42";
    var bar = parseInt(foo, 10) + 1; // bar = 43

The second parameter of the `parseInt()` function is the radix which specifies the number system used by the function. Explicitly define your radix with each function call to avoid unexpected behaviour.

    parseInt('0016'); // parses as 14. The beginning 0 in the string means the browser assumes the octal number system.
    parseInt('0016', 10); // parses as 16. We explicitly set the function to use decimal number system.
