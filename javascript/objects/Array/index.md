---
title: Meta:javascript/objects/Array
---
<p><br />
</p><p><br />
</p>
<div class="editors-only">
<p><b>Merge Candidate</b>:  This page is a candidate for merge with the following pages: [<a rel="nofollow" class="external autonumber" href="http://docs.webplatform.org/wiki/javascript/objects/Array">[1]</a>] 
</p>
</div>
<p><br />
</p><p><br />
</p>
<h2><span class="mw-headline" id="Note">Note</span></h2>
<p>This article seems to be identical clone of MDN's <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array">Array</a>. But I decided to edit it for readability. All links in the article are external.
</p><p>Properties, Examples and Compatibility remain to be edited.
</p>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>The JavaScript Array global object is a constructor for arrays, which are high-level, list-like objects.
</p>
<h2><span class="mw-headline" id="Syntax">Syntax</span></h2>
<ul><li> [element0, element1, ..., elementN]</li></ul>
<ul><li> new Array(<i>element0</i>, <i>element1</i>, ..., <i>elementN</i>)</li></ul>
<ul><li> new Array(<i>arrayLength</i>)</li></ul>
<p><br />
</p>
<dl><dt> element0, element1, ..., elementN</dt>
<dd> A JavaScript array is initialized with the given elements, except in the case where a single argument is passed to the Array constructor and that argument is a number. (See below.) Note that this special case only applies to JavaScript arrays created with the Array constructor, not with array literals created with the bracket syntax.</dd>
<dt> arrayLength</dt>
<dd> If the only argument passed to the Array constructor is an integer between 0 and 2^32^-1  ( 2 to the power of 32 - 1 inclusive), a new, empty JavaScript array and its length is set to that number. If the argument is any other number, a <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError">RangeError</a> exception is thrown.</dd></dl>
<h2><span class="mw-headline" id="Description">Description</span></h2>
<p>Arrays are list-like objects that come with a several built-in methods to perform traversal and mutation operations. Neither the size of a JavaScript array nor the types of its elements are fixed. Since an array's size can grow or shrink at any time, JavaScript arrays are not guaranteed to be dense. In general, these are convenient characteristics; but if these features are not desirable for your particular use case, you might consider using WebGL typed arrays.
</p><p>Note that <a rel="nofollow" class="external text" href="http://www.andrewdupont.net/2006/05/18/javascript-associative-arrays-considered-harmful/">you shouldn't use an array as an associative array</a>. You can use plain <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object">objects</a> instead, although doing so comes with its own caveats. See the post <a rel="nofollow" class="external text" href="http://www.less-broken.com/blog/2010/12/lightweight-javascript-dictionaries.html">Lightweight JavaScript dictionaries with arbitrary keys</a> as an example.
</p>
<h2><span class="mw-headline" id="Accessing_array_elements">Accessing array elements</span></h2>
<p>JavaScript arrays are zero-indexed; the first element of an array is actually at index 0, and the last element is at the index equal to the value of the array's <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length">length</a> property minus 1.
</p>
<pre class="lang-javascript">
var arr = [&quot;this is the first element&quot;, &quot;this is the second element&quot;];
console.log(arr[0]);              // prints &quot;this is the first element&quot;
console.log(arr[1]);              // prints &quot;this is the second element&quot;
console.log(arr[arr.length - 1]); // prints &quot;this is the second element&quot;
</pre>
<p>Array elements are just object properties, in the way that [toString|/en-US/docs/toString] is a property. However, note that trying to access the first element of an array as follows will throw a syntax error:
</p>
<pre class="lang-javascript">
console.log(arr.0);
</pre>
<p><br />
Note that there is nothing unique about JavaScript arrays and their properties that causes this. JavaScript properties that begin with a digit cannot be referenced with dot notation. They must be accessed using bracket notation. For example, if you had an object with a property "3d", it too would have to be referenced using bracket notation, not dot notation. This similarity is exhibited in the following two code samples:
</p>
<pre class="lang-javascript">
var years = [1950, 1960, 1970, 1980, 1990, 2000, 2010];
try {
  console.log(years.0);
}
catch (ex) {
  console.log(&quot;Using bracket notation&quot;);
  console.log(years[0]);
}
</pre>
<pre class="lang-javascript">
try {
  renderer.3d.setTexture(model, &quot;character.png&quot;);
}
catch (ex) {
  console.log(&quot;Using bracket notation&quot;);
  renderer[&quot;3d&quot;].setTexture(model, &quot;character.png&quot;);
}
</pre>
<p>Note that in the 3d example, "3d" had to be quoted. It's possible to quote the JavaScript array indexes as well (e.g., years["2"] instead of years[2]), although it's not necessary. The 2 in years[2] eventually gets coerced into a string by the JavaScript engine, anyway, through an implicit toString conversion. It is for this reason that "2" and "02" would refer to two different slots on the years object and the following example logs true:
</p>
<pre class="lang-javascript">
console.log(years[&quot;2&quot;]&#160;!= years[&quot;02&quot;]);
</pre>
<h3><span class="mw-headline" id="Relationship_between_length_and_numerical_properties">Relationship between <i>length</i> and numerical properties</span></h3>
<p>A JavaScript array's <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length">length</a> property and numerical properties are connected. Several of the built-in array methods (e.g., <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/join">join</a>, <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/slice">slice</a>, <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/indexOf">indexOf</a>, etc.) take into account the value of an array's length property when they're called. Other methods (e.g., <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/push">push</a>, <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/splice">splice</a>, etc.) also result in updates to an array's length property.
</p>
<pre class="lang-javascript">
var fruits = [];
fruits.push(&quot;banana&quot;, &quot;apple&quot;, &quot;peach&quot;);
console.log(fruits.length); // 3
</pre>
<p><br />
When setting a property on a JavaScript array when the property is a valid array index and that index is outside the current bounds of the array, the array will grow to a size large enough to accommodate an element at that index, and the engine will update the array's <i>length</i> property accordingly:
</p>
<pre class="lang-javascript">
fruits[3] = &quot;mango&quot;;
console.log(fruits[3]);
console.log(fruits.length); // 4
</pre>
<p><br />
Setting the <i>length</i> property, directly, also results in special behavior.
</p>
<pre class="lang-javascript">
fruits.length = 10;
console.log(fruits);        // The array gets padded with undefined
console.log(fruits.length); // 10
</pre>
<p><br />
This is explained further on the <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/length">length</a> page.
</p>
<h3><span class="mw-headline" id="Creating_an_array_using_the_result_of_a_match">Creating an array using the result of a match</span></h3>
<p>The result of a match between a regular expression and a string can create a JavaScript array. This array has properties and elements that provide information about the match. An array is the return value of RegExp.exec, String.match, and String.replace. To help explain these properties and elements, look at the following example and then refer to the table below:
</p>
<pre class="lang-javascript">
// Match one d followed by one or more b's followed by one d
// Remember matched b's and the following d
// Ignore case
var myRe = /d(b+)(d)/i;
var myArray = myRe.exec(&quot;cdbBdbsbz&quot;);
</pre>
<p><br />
The properties and elements returned from this match are as follows:
</p>
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
<h2><span class="mw-headline" id="Properties">Properties</span></h2>
<p><a href="/w/index.php?title=Template:Js_see_prototype(%22Array%22,_%22Properties%22)&amp;action=edit&amp;redlink=1" class="new" title="Template:Js see prototype(&quot;Array&quot;, &quot;Properties&quot;) (page does not exist)">Template:Js see prototype("Array", "Properties")</a>
</p>
<dl><dt> [prototype|/en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype]</dt>
<dd> Allows the addition of properties to all objects.</dd></dl>
<pre><a href="/w/index.php?title=Template:jsOverrides(%22Function%22,_%22Properties%22,_%22prototype%22)&amp;action=edit&amp;redlink=1" class="new" title="Template:jsOverrides(&quot;Function&quot;, &quot;Properties&quot;, &quot;prototype&quot;) (page does not exist)">Template:jsOverrides("Function", "Properties", "prototype")</a>
</pre>
<h2><span class="mw-headline" id="Methods">Methods</span></h2>
<pre><a href="/w/index.php?title=Template:Js_see_prototype(%22Array%22,_%22Methods%22)&amp;action=edit&amp;redlink=1" class="new" title="Template:Js see prototype(&quot;Array&quot;, &quot;Methods&quot;) (page does not exist)">Template:Js see prototype("Array", "Methods")</a>
</pre>
<dl><dt> [isArray|/en-US/docs/JavaScript/Reference/Global_Objects/Array/isArray] <a href="/w/index.php?title=Template:js_minversion_inline(%221.8.5%22)&amp;action=edit&amp;redlink=1" class="new" title="Template:js minversion inline(&quot;1.8.5&quot;) (page does not exist)">Template:js minversion inline("1.8.5")</a></dt>
<dd> Return true if a variable is an array, if not false.</dd></dl>
<h2><span class="mw-headline" id="Array_instances">Array instances</span></h2>
<p>Array instances inherit from [Array.prototype|/en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype]. As with all constructors, you can change the constructor's prototype object to make changes to all JavaScript Array instances.
</p>
<h3><span class="mw-headline" id="Properties_2">Properties</span></h3>
<pre><a href="/w/index.php?title=Template:page(%27en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype%27,_%27Properties%27)&amp;action=edit&amp;redlink=1" class="new" title="Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Properties') (page does not exist)">Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Properties')</a>
</pre>
<h3><span class="mw-headline" id="Methods_2">Methods</span></h3>
<h4><span class="mw-headline" id="Mutator_methods">Mutator methods</span></h4>
<pre><a href="/w/index.php?title=Template:page(%27en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype%27,_%27Mutator_methods%27)&amp;action=edit&amp;redlink=1" class="new" title="Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Mutator methods') (page does not exist)">Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Mutator methods')</a>
</pre>
<h4><span class="mw-headline" id="Accessor_methods">Accessor methods</span></h4>
<pre><a href="/w/index.php?title=Template:page(%27en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype%27,_%27Accessor_methods%27)&amp;action=edit&amp;redlink=1" class="new" title="Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Accessor methods') (page does not exist)">Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Accessor methods')</a>
</pre>
<h4><span class="mw-headline" id="Iteration_methods">Iteration methods</span></h4>
<pre><a href="/w/index.php?title=Template:page(%27en-US/docs/JavaScript/Reference/Global_Objects/Array/prototype%27,_%27Iteration_methods%27)&amp;action=edit&amp;redlink=1" class="new" title="Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Iteration methods') (page does not exist)">Template:page('en-US/docs/JavaScript/Reference/Global Objects/Array/prototype', 'Iteration methods')</a>
</pre>
<h2><span class="mw-headline" id="Array_generic_methods">Array generic methods</span></h2>
<p>Sometimes you would like to apply array methods to strings or other array-like objects (such as function [arguments|<a rel="nofollow" class="external free" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Functions_and_function_scope/arguments">https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Functions_and_function_scope/arguments</a>]). By doing this, you treat a string as an array of characters (or otherwise treat a non-array as an array). For example, in order to check that every character in the variable str is a letter, you would write:
</p>
<pre class="lang-javascript">
function isLetter(character) {
  return (character &gt;= &quot;a&quot; &amp;&amp; character &lt;= &quot;z&quot;);
}

if (Array.prototype.every.call(str, isLetter))
  alert(&quot;The string '&quot; + str + &quot;' contains only letters!&quot;);
</pre>
<p><br />
This notation is rather wasteful and JavaScript 1.6 introduced a generic shorthand:
</p>
<pre class="lang-javascript">
if (Array.every(isLetter, str))
  alert(&quot;The string '&quot; + str + &quot;' contains only letters!&quot;);
</pre>
<p><br />
[Generics|<a rel="nofollow" class="external free" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String#String_generic_methods">https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String#String_generic_methods</a>] are also available on [String|<a rel="nofollow" class="external free" href="https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String">https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String</a>].
</p><p>These are currently not part of ECMAScript standards (though the ES6 [Array.from()|<a rel="nofollow" class="external free" href="https://github.com/monolithed/ECMAScript-6">https://github.com/monolithed/ECMAScript-6</a>] can be used to achieve this). The following is a shim to allow its use in all browsers:
</p>
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

  for (i = 0; i &lt; methodCount; i++) {
    assignArrayGeneric(methods[i]);
  }
}());
</pre>
<p><br />
</p>
<h2><span class="mw-headline" id="Examples">Examples</span></h2>
<h2><span class="mw-headline" id="Example:_Creating_an_array">Example: Creating an array</span></h2>
<p>The following example creates an array, msgArray, with a length of 0, then assigns values to msgArray[0] and msgArray[99], changing the length of the array to 100.
</p>
<pre class="lang-javascript">
var msgArray = new Array();
msgArray[0] = &quot;Hello&quot;;
msgArray[99] = &quot;world&quot;;

if (msgArray.length == 100)
   print(&quot;The length is 100.&quot;);
</pre>
<h3><span class="mw-headline" id="Example:_Creating_a_two-dimensional_array">Example: Creating a two-dimensional array</span></h3>
<p>The following creates chess board as a two dimensional array of strings. The first move is made by copying the 'p' in 6,4 to 4,4. The old position 6,4 is made blank.
</p>
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
<p><br />
Here is the output:
</p><p>R,N,B,Q,K,B,N,R
P,P,P,P,P,P,P,P
</p>
<pre>, , , , , , , 
, , , , , , , 
, , , , , , , 
, , , , , , , 
</pre>
<p>p,p,p,p,p,p,p,p
r,n,b,q,k,b,n,r
</p><p>R,N,B,Q,K,B,N,R
P,P,P,P,P,P,P,P
</p>
<pre>, , , , , , , 
, , , , , , , 
, , , ,p, , , 
, , , , , , , 
</pre>
<p>p,p,p,p, ,p,p,p
r,n,b,q,k,b,n,r
</p>
<h2><span class="mw-headline" id="Browser_compatibility">Browser compatibility</span></h2>
<p><a href="/w/index.php?title=Template:CompatibilityTable&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatibilityTable (page does not exist)">Template:CompatibilityTable</a>
</p><p>FeatureChromeFirefox (Gecko)Internet ExplorerOperaSafari (WebKit)Basic support<a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a><a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a><a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a><a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a><a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a>FeatureAndroidFirefox Mobile (Gecko)IE PhoneOpera MobileSafari MobileBasic support<a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a><a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a><a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a><a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a><a href="/w/index.php?title=Template:CompatVersionUnknown&amp;action=edit&amp;redlink=1" class="new" title="Template:CompatVersionUnknown (page does not exist)">Template:CompatVersionUnknown</a>
</p>
<h2><span class="mw-headline" id="See_also">See also</span></h2>
<ul><li> <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/Guide/Working_with_Objects#Indexing_object_properties">"Indexing object properties" in JavaScript Guide: "Working with objects"</a></li>
<li> <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/New_in_JavaScript/1.7#Array_comprehensions">New in JavaScript 1.7: Array comprehensions</a></li>
<li> <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript/New_in_JavaScript/1.6#Array_extras">New in JavaScript 1.6: Array extras</a></li>
<li> <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/JavaScript_typed_arrays">Draft: Typed Arrays</a></li></ul>

<!-- Saved in parser cache with key wpwiki:pcache:idhash:8294-0!*!0!!*!*!*!esi=1 and timestamp 20150731181924 and revision id 45445
 -->
