---
title: 'parseFloat'
tags:
  - JavaScript
todo_broken_links:
  note: 'During import MediaWiki could not find the following links, please fix and adjust this list.'
  links:
    - javascript/functions/isNaN
uri: 'Meta:javascript/functions/parseFloat'

---
**Merge Candidate**: This page is a candidate for merge with the following pages: [[[1]](http://docs.webplatform.org/wiki/javascript/parseFloat)]

The `parseFloat()` function returns the first number that it finds in the `String` argument. If the first character cannot be converted to a number, it returns `NaN`.

    parseFloat("42"); // parses as 42
    parseFloat("12.34 56.78"); // parses as 12.34
    parseFloat("314e-2"); // parses as 3.14
    parseFloat("99bottles"); // parses as 99
    parseFloat("Bottles99"); // parses as NaN

You can use `isNaN()` to test for the returned value of `NaN`.
