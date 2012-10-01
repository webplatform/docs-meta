{{Page_Title}}
{{Flags
|High-level issues=Merge Candidate
}}
{{Standardization_Status}}
{{API_Name}}
{{Summary_Section}}
{{Markup_Element
|Content=

<div style='float: right;background: white;border:1px dashed black;padding: 1ex;margin-left:1ex;'>

* [[HTML/Elements|List of Elements]]
** [[HTML/Elements#Text-level_semantics|Text-level semantics]]
*** [[HTML/Elements/a|a]]
*** [[HTML/Elements/em|em]]
*** [[HTML/Elements/strong|strong]]
*** [[HTML/Elements/small|small]]
*** [[HTML/Elements/s|s]]
*** [[HTML/Elements/cite|cite]]
*** [[HTML/Elements/q|q]]
*** [[HTML/Elements/dfn|dfn]]
*** [[HTML/Elements/abbr|abbr]]
*** [[HTML/Elements/time|time]]
*** [[HTML/Elements/code|code]]
*** [[HTML/Elements/var|var]]
*** [[HTML/Elements/samp|samp]]
*** [[HTML/Elements/kbd|kbd]]
*** [[HTML/Elements/sub|sub]]
*** [[HTML/Elements/sup|sup]]
*** [[HTML/Elements/i|i]]
*** [[HTML/Elements/b|b]]
*** [[HTML/Elements/mark|mark]]
*** [[HTML/Elements/ruby|ruby]]
*** [[HTML/Elements/rt|rt]]
*** [[HTML/Elements/rp|rp]]
*** [[HTML/Elements/bdo|bdo]]
*** [[HTML/Elements/span|span]]
*** [[HTML/Elements/br|br]]
*** [[HTML/Elements/wbr|wbr]]
*** [[HTML/Elements/tt|tt]]
*** [[HTML/Elements/u|u]]
*** [[HTML/Elements/strike|strike]]
*** [[HTML/Elements/big|big]]
*** [[HTML/Elements/basefont|basefont]]
*** [[HTML/Elements/font|font]]
*** [[HTML/Elements/acronym|acronym]]
*** [[HTML/Elements/blink|blink]]
*** [[HTML/Elements/marquee|marquee]]
*** [[HTML/Elements/nobr|nobr]]
*** [[HTML/Elements/spacer|spacer]]
*** [[HTML/Elements/listing|listing]]
*** [[HTML/Elements/xmp|xmp]]
*** [[HTML/Elements/nextid|nextid]]

</div>

= &lt;var&gt; =

The &lt;var&gt; element represents a variable.

== Point ==

*This element could be an actual variable in a mathematical expression or programming context.


== HTML Attributes ==

See [[HTML/Attributes/_Global|global attributes]].


== Examples ==

=== Example A ===
In the paragraph below, the letter "n" is being used as a variable in prose [try it]:
<pre>
<p>If there are <var>n</var> pipes leading to the ice
cream factory then I expect at <em>least</em> <var>n</var>
flavors of ice cream to be available for purchase!</p>
</pre>

[[File:Var01.png]]

=== Example B ===
In this example, an equation is shown, with a legend that references the variables in the equation. The expression itself is marked up with MathML, but the variables are mentioned in the figure's legend using a var element [try it]:

<pre>
<figure>
 <math>
  <mi>a</mi>
  <mo>=</mo>
  <msqrt>
   <msup><mi>b</mi><mn>2</mn></msup>
   <mi>+</mi>
   <msup><mi>c</mi><mn>2</mn></msup>
  </msqrt>
 </math>
 <figcaption>
  Using Pythagoras' theorem to solve for the hypotenuse <var>a</var> of
  a triangle with sides <var>b</var> and <var>c</var>
 </figcaption>
</figure>
</pre>

[[File:Var02.png]]

== HTML Reference ==

The HTML5 specification defines the &lt;var&gt; element in [http://www.w3.org/TR/html5/text-level-semantics.html#the-var-element 4.6.12 The var element].

[[Category:HTML]]
[[Category:HTMLElement]]

}}
{{Examples_Section
|Not_required=No
|Examples=
}}
{{Notes_Section}}
{{Related_Specifications_Section
|Specifications=
}}
{{Compatibility_Section
|Not_required=No
|Desktop_rows=
|Mobile_rows=
|Notes_rows=
}}
{{See_Also_Section}}
{{Topics|HTML}}
{{External_Attribution
|Is_CC-BY-SA=No
|MDN_link=
|MSDN_link=
|HTML5Rocks_link=
}}