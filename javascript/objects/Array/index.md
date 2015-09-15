---
title: Array
todo_broken_links:
  note: 'During import MediaWiki could not find the following links, please fix and adjust this list.'
  links:
    - 'Template:Js see prototype("Array", "Properties")'
    - 'Template:jsOverrides("Function", "Properties", "prototype")'
    - 'Template:Js see prototype("Array", "Methods")'
    - 'Template:js minversion inline("1.8.5")'
    - 'Template:page(''en-US/docs/JavaScript/Reference/Global Objects/Array/prototype'', ''Properties'')'
    - 'Template:page(''en-US/docs/JavaScript/Reference/Global Objects/Array/prototype'', ''Mutator methods'')'
    - 'Template:page(''en-US/docs/JavaScript/Reference/Global Objects/Array/prototype'', ''Accessor methods'')'
    - 'Template:page(''en-US/docs/JavaScript/Reference/Global Objects/Array/prototype'', ''Iteration methods'')'
    - 'Template:CompatibilityTable'
    - 'Template:CompatVersionUnknown'
uri: 'Meta:javascript/objects/Array'

---
**Merge Candidate**: This page is a candidate for merge with the following pages: [[[1]](http://docs.webplatform.org/wiki/javascript/objects/Array)]

## <span>Note</span>

This article seems to be identical clone of MDN's [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). But I decided to edit it for readability. All links in the article are external.

Properties, Examples and Compatibility remain to be edited.

## <span>Summary</span>

The JavaScript Array global object is a constructor for arrays, which are high-level, list-like objects.

## <span>Syntax</span>

-   [element0, element1, ..., elementN]

-   new Array(*element0*, *element1*, ..., *elementN*)

-   new Array(*arrayLength*)

 element0, element1, ..., elementN
:   A JavaScript array is initialized with the given elements, except in the case where a single argument is passed to the Array constructor and that argument is a number. (See below.) Note that this special case only applies to JavaScript arrays created with the Array constructor, not with array literals created with the bracket syntax.
 arrayLength
:   If the only argument passed to the Array constructor is an integer between 0 and 2\^32\^-1 ( 2 to the power of 32 - 1 inclusive), a new, empty JavaScript array and its length is set to that number. If the argument is any other number, a [RangeError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError) exception is thrown.

## <span>Description</span>

Arrays are list-like objects that come with a several built-in methods to perform traversal and mutation operations. Neither the size of a JavaScript array nor the types of its elements are fixed. Since an array's size can grow or shrink at any time, JavaScript arrays are not guaranteed to be dense. In general, these are convenient characteristics; but if these features are not desirable for your particular use case, you might consider using WebGL typed arrays.

Note that [you shouldn't use an array as an associative array](http://www.andrewdupont.net/2006/05/18/javascript-associative-arrays-considered-harmful/). You can use plain [objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) instead, although doing so comes with its own caveats. See the post [Lightweight JavaScript dictionaries with arbitrary keys](http://www.less-broken.com/blog/2010/12/lightweight-javascript-dictionaries.html) as an example.

## <span>Accessing array elements</span>

JavaScript arrays are zero-indexed; the first element of an array is actually at index 0, and the last element is at the index equal to the value of the array's [length](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length) property minus 1.

```
var arr = ["this is the first element", "this is the second element"];
console.log(arr[0]);              // prints "this is the first element"
console.log(arr[1]);              // prints "this is the second element"
console.log(arr[arr.length - 1]); // prints "this is the second element"
```

Array elements are just object properties, in the way that [toString|/en-US/docs/toString] is a property. However, note that trying to access the first element of an array as follows will throw a syntax error:

```
console.log(arr.0);
```

 Note that there is nothing unique about JavaScript arrays and their properties that causes this. JavaScript properties that begin with a digit cannot be referenced with dot notation. They must be accessed using bracket notation. For example, if you had an object with a property "3d", it too would have to be referenced using bracket notation, not dot notation. This similarity is exhibited in the following two code samples:

```
var years = [1950, 1960, 1970, 1980, 1990, 2000, 2010];
try {
  console.log(years.0);
}
catch (ex) {
  console.log("Using bracket notation");
  console.log(years[0]);
}
```

```
try {
  renderer.3d.setTexture(model, "character.png");
}
catch (ex) {
  console.log("Using bracket notation");
  renderer["3d"].setTexture(model, "character.png");
}
```

Note that in the 3d example, "3d" had to be quoted. It's possible to quote the JavaScript array indexes as well (e.g., years["2"] instead of years[2]), although it's not necessary. The 2 in years[2] eventually gets coerced into a string by the JavaScript engine, anyway, through an implicit toString conversion. It is for this reason that "2" and "02" would refer to two different slots on the years object and the following example logs true:

```
console.log(years["2"] != years["02"]);
```

### <span>Relationship between *length* and numerical properties</span>

A JavaScript array's [length](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length) property and numerical properties are connected. Several of the built-in array methods (e.g., [join](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/join), [slice](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/slice), [indexOf](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/indexOf), etc.) take into account the value of an array's length property when they're called. Other methods (e.g., [push](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/push), [splice](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/splice), etc.) also result in updates to an array's length property.

```
var fruits = [];
fruits.push("banana", "apple", "peach");
console.log(fruits.length); // 3
```

 When setting a property on a JavaScript array when the property is a valid array index and that index is outside the current bounds of the array, the array will grow to a size large enough to accommodate an element at that index, and the engine will update the array's *length* property accordingly:

```
fruits[3] = "mango";
console.log(fruits[3]);
console.log(fruits.length); // 4
```

 Setting the *length* property, directly, also results in special behavior.

```
fruits.length = 10;
console.log(fruits);        // The array gets padded with undefined
console.log(fruits.length); // 10
```

 This is explained further on the [length](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length) page.

### <span>Creating an array using the result of a match</span>

The result of a match between a regular expression and a string can create a JavaScript array. This array has properties and elements that provide information about the match. An array is the return value of RegExp.exec, String.match, and String.replace. To help explain these properties and elements, look at the following example and then refer to the table below:

```
// Match one d followed by one or more b's followed by one d
// Remember matched b's and the following d
// Ignore case
var myRe = /d(b+)(d)/i;
var myArray = myRe.exec("cdbBdbsbz");
```

 The properties and elements returned from this match are as follows:

|Property/Element|Description|Example|
|:---------------|:----------|:------|
|input|A read-only property that reflects the original string against which the regular expression was matched.|cdbBdbsbz|
|index|A read-only property that is the zero-based index of the match in the string.|1|
|[0]|A read-only element that specifies the last matched characters.|dbBd|
|[1], ...[n]|Read-only elements that specify the parenthesized substring matches, if included in the regular expression. The number of possible parenthesized substrings is unlimited.|[1]: bB\\\\ [2]: d|

## <span>Properties</span>

[Template:Js see prototype("Array", "Properties")](/w/index.php?title=Template:Js_see_prototype(%22Array%22,_%22Properties%22)&action=edit&redlink=1)

 [prototype|/en-US/docs/JavaScript/Reference/Global\_Objects/Array/prototype]
:   Allows the addition of properties to all objects.

<!-- -->

    Template:jsOverrides("Function", "Properties", "prototype")

## <span>Methods</span>

    Template:Js see prototype("Array", "Methods")

 [isArray|/en-US/docs/JavaScript/Reference/Global\_Objects/Array/isArray] [Template:js minversion inline("1.8.5")](/w/index.php?title=Template:js_minversion_inline(%221.8.5%22)&action=edit&redlink=1)
:   Return true if a variable is an array, if not false.

## <span>Array instances</span>

Array instances inherit from [Array.prototype|/en-US/docs/JavaScript/Reference/Global\_Objects/Array/prototype]. As with all constructors, you can change the constructor's prototype object to make changes to all JavaScript Array instances.

### <span>Properties</span>

    Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Properties')

### <span>Methods</span>

#### <span>Mutator methods</span>

    Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Mutator methods')

#### <span>Accessor methods</span>

    Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Accessor methods')

#### <span>Iteration methods</span>

    Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Iteration methods')

## <span>Array generic methods</span>

Sometimes you would like to apply array methods to strings or other array-like objects (such as function [arguments|<https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Functions_and_function_scope/arguments>]). By doing this, you treat a string as an array of characters (or otherwise treat a non-array as an array). For example, in order to check that every character in the variable str is a letter, you would write:

```
function isLetter(character) {
  return (character >= "a" && character <= "z");
}

if (Array.prototype.every.call(str, isLetter))
  alert("The string '" + str + "' contains only letters!");
```

 This notation is rather wasteful and JavaScript 1.6 introduced a generic shorthand:

```
if (Array.every(isLetter, str))
  alert("The string '" + str + "' contains only letters!");
```

 [Generics|<https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String#String_generic_methods>] are also available on [String|<https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String>].

These are currently not part of ECMAScript standards (though the ES6 [Array.from()|<https://github.com/monolithed/ECMAScript-6>] can be used to achieve this). The following is a shim to allow its use in all browsers:

```
/*globals define*/
// Assumes Array extras already present (one may use shims for these as well)
(function () {
  'use strict';

  var i,
    // We could also build the array of methods with the following, but the
    //   getOwnPropertyNames() method is non-shimable:
    // Object.getOwnPropertyNames(Array).filter(function (methodName) {return typeof Array[methodName] === 'function'});
    methods = [
        'join', 'reverse', 'sort', 'push', 'pop', 'shift', 'unshift',
        'splice', 'concat', 'slice', 'indexOf', 'lastIndexOf',
        'forEach', 'map', 'reduce', 'reduceRight', 'filter',
        'some', 'every', 'isArray'
    ],
    methodCount = methods.length,
    assignArrayGeneric = function (methodName) {
      var method = Array.prototype[methodName];
      Array[methodName] = function (arg1) {
        return method.apply(arg1, Array.prototype.slice.call(arguments, 1));
      };
    };

  for (i = 0; i < methodCount; i++) {
    assignArrayGeneric(methods[i]);
  }
}());
```

## <span>Examples</span>

## <span>Example: Creating an array</span>

The following example creates an array, msgArray, with a length of 0, then assigns values to msgArray[0] and msgArray[99], changing the length of the array to 100.

```
var msgArray = new Array();
msgArray[0] = "Hello";
msgArray[99] = "world";

if (msgArray.length == 100)
   print("The length is 100.");
```

### <span>Example: Creating a two-dimensional array</span>

The following creates chess board as a two dimensional array of strings. The first move is made by copying the 'p' in 6,4 to 4,4. The old position 6,4 is made blank.

```
var board =
[ ['R','N','B','Q','K','B','N','R'],
  ['P','P','P','P','P','P','P','P'],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  ['p','p','p','p','p','p','p','p'],
  ['r','n','b','q','k','b','n','r']];
print(board.join('\n') + '\n\n');

// Move King's Pawn forward 2
board[4][4] = board[6][4];
board[6][4] = ' ';
print(board.join('\n'));
```

 Here is the output:

R,N,B,Q,K,B,N,R P,P,P,P,P,P,P,P

    , , , , , , ,
    , , , , , , ,
    , , , , , , ,
    , , , , , , ,

p,p,p,p,p,p,p,p r,n,b,q,k,b,n,r

R,N,B,Q,K,B,N,R P,P,P,P,P,P,P,P

    , , , , , , ,
    , , , , , , ,
    , , , ,p, , ,
    , , , , , , ,

p,p,p,p, ,p,p,p r,n,b,q,k,b,n,r

## <span>Browser compatibility</span>

[Template:CompatibilityTable](/w/index.php?title=Template:CompatibilityTable&action=edit&redlink=1)

FeatureChromeFirefox (Gecko)Internet ExplorerOperaSafari (WebKit)Basic support[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)FeatureAndroidFirefox Mobile (Gecko)IE PhoneOpera MobileSafari MobileBasic support[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)[Template:CompatVersionUnknown](/w/index.php?title=Template:CompatVersionUnknown&action=edit&redlink=1)

## <span>See also</span>

-   ["Indexing object properties" in JavaScript Guide: "Working with objects"](https://developer.mozilla.org/en-US/docs/JavaScript/Guide/Working_with_Objects#Indexing_object_properties)
-   [New in JavaScript 1.7: Array comprehensions](https://developer.mozilla.org/en-US/docs/JavaScript/New_in_JavaScript/1.7#Array_comprehensions)
-   [New in JavaScript 1.6: Array extras](https://developer.mozilla.org/en-US/docs/JavaScript/New_in_JavaScript/1.6#Array_extras)
-   [Draft: Typed Arrays](https://developer.mozilla.org/en-US/docs/JavaScript_typed_arrays)
