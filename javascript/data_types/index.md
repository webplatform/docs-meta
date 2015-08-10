---
title: Meta:javascript/data types
path: javascript/data_types

---
<h1><span class="mw-headline" id="JavaScript_data_types">JavaScript data types</span></h1>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>Index page for JavaScript data types
</p><p><br />
</p><p><br />
</p>
<div class="editors-only">
<p><b>Merge Candidate</b>:  This page is a candidate for merge with the following pages:  
</p>
</div>
<p><br />
</p><p><br />
</p>
<h2><span class="mw-headline" id="Introduction">Introduction</span></h2>
<p>Unlike other programming languages every thing in JavaScript is a object, this includes arrays(lists), functions, strings, and numbers. There are 6 types defined by ECMAScript: <code>Undefined</code>, <code>Null</code>, <code>Boolean</code>, <code>String</code>, <code>Number</code> and <code>Object</code>.
</p><p>As functions are objects in JavaScript they can be passed as normal data, which means this would work:
</p><p><code>SomeFunction(1, function(error) { console.log(error);});</code>
</p><p>in JavaScript and wouldn't in most other languages.
</p><p>Also in JavaScript there are two ways to create Variables:
</p><p>1. The Object way:
</p>
<pre class="language-javascript" data-lang="javascript">
//A string
var string = new String("Hello World!");
//An array
var array = new Array("H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!");
//A number
var number = new Number(435560967531);
// or 
var number = new Number("435560967531");
</pre>
<p><br />
2.The way used in most other languages:
</p><p><br />
</p>
<pre class="language-javascript" data-lang="javascript">
//A string
var string = "Hello World!";
//An array
var array = ["H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!"];
//A number
var number = 435560967531;
</pre>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>
