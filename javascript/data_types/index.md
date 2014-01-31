{{Page_Title|JavaScript data types}}
{{Flags
|High-level issues=Merge Candidate, Needs Topics, Missing Relevant Sections
|Checked_Out=No
}}
{{Summary_Section|Index page for JavaScript data types}}
{{Basic Page}}
{{Editorial/Merge_Candidate}}

{{Special:PrefixIndex/js/data types/}}

==Introduction==
Unlike other programming languages every thing in JavaScript is a object, this includes arrays(lists), functions, strings, and numbers. There are 6 types defined by ECMAScript: <code>Undefined</code>, <code>Null</code>, <code>Boolean</code>, <code>String</code>, <code>Number</code> and <code>Object</code>.

As functions are objects in JavaScript they can be passed as normal data, which means this would work:

<code>SomeFunction(1, function(error) { console.log(error);});</code>

in JavaScript and wouldn't in most other languages.

Also in JavaScript there are two ways to create Variables:

1. The Object way:
<Syntaxhighlight lang="javascript">
//A string
var string = new String("Hello World!");
//An array
var array = new Array("H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!");
//A number
var number = new Number(435560967531);
// or 
var number = new Number("435560967531");
</Syntaxhighlight>

2.The way used in most other languages:

<Syntaxhighlight lang="javascript">
//A string
var string = "Hello World!";
//An array
var array = ["H", "e", "l", "l", "o", " ", "W", "o", "r", "l", "d", "!"];
//A number
var number = 435560967531;

</Syntaxhighlight>
{{Notes_Section}}
{{Topics|JavaScript}}
{{External_Attribution
|Is_CC-BY-SA=No
|MDN_link=
|MSDN_link=
|HTML5Rocks_link=
}}