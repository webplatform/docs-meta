---
title: JavaScript data types
summary: 'Index page for JavaScript data types'
tags:
  - Basic
  - Pages
  - JavaScript
uri: 'Meta:javascript/data types'

---
## Summary

Index page for JavaScript data types

**Merge Candidate**: This page is a candidate for merge with the following pages:

## Introduction

Unlike other programming languages every thing in JavaScript is a object, this includes arrays(lists), functions, strings, and numbers. There are 6 types defined by ECMAScript: `Undefined`, `Null`, `Boolean`, `String`, `Number` and `Object`.

As functions are objects in JavaScript they can be passed as normal data, which means this would work:

`SomeFunction(1, function(error) { console.log(error);});`

in JavaScript and wouldn't in most other languages.

Also in JavaScript there are two ways to create Variables:

1. The Object way:

``` js
//A string
var string = new String("Hello World!");
//An array
var array = new Array("H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!");
//A number
var number = new Number(435560967531);
// or
var number = new Number("435560967531");
```

 2.The way used in most other languages:

``` js
//A string
var string = "Hello World!";
//An array
var array = ["H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!"];
//A number
var number = 435560967531;
```
