{{Editorial/Merge_Candidate|Other=http://docs.webplatform.org/wiki/javascript/objects/Array}}


== Note ==

This article seems to be identical clone of MDN's [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array Array]. But I decided to edit it for readability. All links in the article are external.

Properties, Examples and Compatibility remain to be edited.

== Summary ==

The JavaScript Array global object is a constructor for arrays, which are high-level, list-like objects.

== Syntax ==

* [element0, element1, ..., elementN]

* new Array(''element0'', ''element1'', ..., ''elementN'')

* new Array(''arrayLength'')


; element0, element1, ..., elementN
: A JavaScript array is initialized with the given elements, except in the case where a single argument is passed to the Array constructor and that argument is a number. (See below.) Note that this special case only applies to JavaScript arrays created with the Array constructor, not with array literals created with the bracket syntax.
; arrayLength
: If the only argument passed to the Array constructor is an integer between 0 and 2^32^-1  ( 2 to the power of 32 - 1 inclusive), a new, empty JavaScript array and its length is set to that number. If the argument is any other number, a [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError RangeError] exception is thrown.

== Description ==

Arrays are list-like objects that come with a several built-in methods to perform traversal and mutation operations. Neither the size of a JavaScript array nor the types of its elements are fixed. Since an array's size can grow or shrink at any time, JavaScript arrays are not guaranteed to be dense. In general, these are convenient characteristics; but if these features are not desirable for your particular use case, you might consider using WebGL typed arrays.

Note that [http://www.andrewdupont.net/2006/05/18/javascript-associative-arrays-considered-harmful/ you shouldn't use an array as an associative array]. You can use plain [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object objects] instead, although doing so comes with its own caveats. See the post [http://www.less-broken.com/blog/2010/12/lightweight-javascript-dictionaries.html Lightweight JavaScript dictionaries with arbitrary keys] as an example.

== Accessing array elements ==

JavaScript arrays are zero-indexed; the first element of an array is actually at index 0, and the last element is at the index equal to the value of the array's [https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length length] property minus 1.

<pre class="lang-javascript">
var arr = ["this is the first element", "this is the second element"];
console.log(arr[0]);              // prints "this is the first element"
console.log(arr[1]);              // prints "this is the second element"
console.log(arr[arr.length - 1]); // prints "this is the second element"
</pre>

Array elements are just object properties, in the way that [toString|/en-US/docs/toString] is a property. However, note that trying to access the first element of an array as follows will throw a syntax error:

<pre class="lang-javascript">
console.log(arr.0);
</pre>


Note that there is nothing unique about JavaScript arrays and their properties that causes this. JavaScript properties that begin with a digit cannot be referenced with dot notation. They must be accessed using bracket notation. For example, if you had an object with a property "3d", it too would have to be referenced using bracket notation, not dot notation. This similarity is exhibited in the following two code samples:

<pre class="lang-javascript">
var years = [1950, 1960, 1970, 1980, 1990, 2000, 2010];
try {
  console.log(years.0);
}
catch (ex) {
  console.log("Using bracket notation");
  console.log(years[0]);
}
</pre>

<pre class="lang-javascript">
try {
  renderer.3d.setTexture(model, "character.png");
}
catch (ex) {
  console.log("Using bracket notation");
  renderer["3d"].setTexture(model, "character.png");
}
</pre>

Note that in the 3d example, "3d" had to be quoted. It's possible to quote the JavaScript array indexes as well (e.g., years["2"] instead of years[2]), although it's not necessary. The 2 in years[2] eventually gets coerced into a string by the JavaScript engine, anyway, through an implicit toString conversion. It is for this reason that "2" and "02" would refer to two different slots on the years object and the following example logs true:

<pre class="lang-javascript">
console.log(years["2"] != years["02"]);
</pre>

=== Relationship between ''length'' and numerical properties ===

A JavaScript array's [https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length length] property and numerical properties are connected. Several of the built-in array methods (e.g., [https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/join join], [https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/slice slice], [https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/indexOf indexOf], etc.) take into account the value of an array's length property when they're called. Other methods (e.g., [https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/push push], [https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/splice splice], etc.) also result in updates to an array's length property.

<pre class="lang-javascript">
var fruits = [];
fruits.push("banana", "apple", "peach");
console.log(fruits.length); // 3
</pre>


When setting a property on a JavaScript array when the property is a valid array index and that index is outside the current bounds of the array, the array will grow to a size large enough to accommodate an element at that index, and the engine will update the array's ''length'' property accordingly:

<pre class="lang-javascript">
fruits[3] = "mango";
console.log(fruits[3]);
console.log(fruits.length); // 4
</pre>


Setting the ''length'' property, directly, also results in special behavior.

<pre class="lang-javascript">
fruits.length = 10;
console.log(fruits);        // The array gets padded with undefined
console.log(fruits.length); // 10
</pre>


This is explained further on the [https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length length] page.

=== Creating an array using the result of a match ===

The result of a match between a regular expression and a string can create a JavaScript array. This array has properties and elements that provide information about the match. An array is the return value of RegExp.exec, String.match, and String.replace. To help explain these properties and elements, look at the following example and then refer to the table below:

<pre class="lang-javascript">
// Match one d followed by one or more b's followed by one d
// Remember matched b's and the following d
// Ignore case
var myRe = /d(b+)(d)/i;
var myArray = myRe.exec("cdbBdbsbz");
</pre>


The properties and elements returned from this match are as follows:

<table>
    <tr>
        <th>Property/Element</th>
        <th>Description</th>
        <th>Example</th>
    </tr>
    <tr>
        <td>input</td>
        <td>A read-only property that reflects the original string against which the regular expression was matched.</td>
        <td>cdbBdbsbz</td>
    </tr>
    <tr>
        <td>index</td>
        <td>A read-only property that is the zero-based index of the match in the string. </td>
        <td>1</td>
    </tr>
    <tr>
        <td>[0]</td>
        <td>A read-only element that specifies the last matched characters.</td>
        <td>dbBd</td>
    </tr>
    <tr>
        <td>[1], ...[n]</td>
        <td> Read-only elements that specify the parenthesized substring matches, if included in the regular expression. The number of possible parenthesized substrings is unlimited.</td>
        <td>[1]: bB\\ [2]: d</td>
    </tr>
</table>

== Properties ==

{{ Js_see_prototype("Array", "Properties") }}

; [prototype|/en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype]
: Allows the addition of properties to all objects.

 {{ jsOverrides("Function", "Properties", "prototype") }}

== Methods ==

 {{ Js_see_prototype("Array", "Methods") }}

; [isArray|/en-US/docs/JavaScript/Reference/Global_Objects/Array/isArray] {{ js_minversion_inline("1.8.5") }}
: Return true if a variable is an array, if not false.

== Array instances ==

Array instances inherit from [Array.prototype|/en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype]. As with all constructors, you can change the constructor's prototype object to make changes to all JavaScript Array instances.

=== Properties ===

 {{ page('en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype', 'Properties') }}

=== Methods ===

==== Mutator methods ====

 {{ page('en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype', 'Mutator_methods') }}

==== Accessor methods ====

 {{ page('en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype', 'Accessor_methods') }}

==== Iteration methods ====

 {{ page('en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype', 'Iteration_methods') }}

== Array generic methods ==

Sometimes you would like to apply array methods to strings or other array-like objects (such as function [arguments|https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Functions_and_function_scope/arguments]). By doing this, you treat a string as an array of characters (or otherwise treat a non-array as an array). For example, in order to check that every character in the variable str is a letter, you would write:

<pre class="lang-javascript">
function isLetter(character) {
  return (character >= "a" && character <= "z");
}

if (Array.prototype.every.call(str, isLetter))
  alert("The string '" + str + "' contains only letters!");
</pre>


This notation is rather wasteful and JavaScript 1.6 introduced a generic shorthand:

<pre class="lang-javascript">
if (Array.every(isLetter, str))
  alert("The string '" + str + "' contains only letters!");
</pre>


[Generics|https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String#String_generic_methods] are also available on [String|https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String].

These are currently not part of ECMAScript standards (though the ES6 [Array.from()|https://github.com/monolithed/ECMAScript-6] can be used to achieve this). The following is a shim to allow its use in all browsers:

<pre class="lang-javascript">
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
</pre>


== Examples ==

== Example: Creating an array ==

The following example creates an array, msgArray, with a length of 0, then assigns values to msgArray[0] and msgArray[99], changing the length of the array to 100.

<pre class="lang-javascript">
var msgArray = new Array();
msgArray[0] = "Hello";
msgArray[99] = "world";

if (msgArray.length == 100)
   print("The length is 100.");
</pre>

=== Example: Creating a two-dimensional array ===

The following creates chess board as a two dimensional array of strings. The first move is made by copying the 'p' in 6,4 to 4,4. The old position 6,4 is made blank.

<pre class="lang-javascript">
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
</pre>


Here is the output:

R,N,B,Q,K,B,N,R
P,P,P,P,P,P,P,P
 , , , , , , , 
 , , , , , , , 
 , , , , , , , 
 , , , , , , , 
p,p,p,p,p,p,p,p
r,n,b,q,k,b,n,r

R,N,B,Q,K,B,N,R
P,P,P,P,P,P,P,P
 , , , , , , , 
 , , , , , , , 
 , , , ,p, , , 
 , , , , , , , 
p,p,p,p, ,p,p,p
r,n,b,q,k,b,n,r

== Browser compatibility ==

{{ CompatibilityTable }}

FeatureChromeFirefox (Gecko)Internet ExplorerOperaSafari (WebKit)Basic support{{ CompatVersionUnknown }}{{ CompatVersionUnknown }}{{ CompatVersionUnknown }}{{ CompatVersionUnknown }}{{ CompatVersionUnknown }}FeatureAndroidFirefox Mobile (Gecko)IE PhoneOpera MobileSafari MobileBasic support{{ CompatVersionUnknown }}{{ CompatVersionUnknown }}{{ CompatVersionUnknown }}{{ CompatVersionUnknown }}{{ CompatVersionUnknown }}

== See also ==

* [https://developer.mozilla.org/en-US/docs/JavaScript/Guide/Working_with_Objects#Indexing_object_properties "Indexing object properties" in JavaScript Guide: "Working with objects"]
* [https://developer.mozilla.org/en-US/docs/JavaScript/New_in_JavaScript/1.7#Array_comprehensions New in JavaScript 1.7: Array comprehensions]
* [https://developer.mozilla.org/en-US/docs/JavaScript/New_in_JavaScript/1.6#Array_extras New in JavaScript 1.6: Array extras]
* [https://developer.mozilla.org/en-US/docs/JavaScript_typed_arrays Draft: Typed Arrays]