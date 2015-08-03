---
title: Meta:web platform wednesday/js basic facts tasks
---
<h3><span class="mw-headline" id="Compare_the_WPD_page_to_the_original_Microsoft_Developer_Network_article_linked_from_the_bottom_of_the_page">Compare the WPD page to the original Microsoft Developer Network article linked from the bottom of the page</span></h3>
<p>If any content didn't make it through the import, add it to WPD page.
</p><p>Example:
</p>
<ul><li> <a rel="nofollow" class="external free" href="http://docs.webplatform.org/wiki/javascript/Array">http://docs.webplatform.org/wiki/javascript/Array</a></li>
<li> <a rel="nofollow" class="external free" href="http://msdn.microsoft.com/en-us/library/ie/k4h76zbx(v=vs.94).aspx">http://msdn.microsoft.com/en-us/library/ie/k4h76zbx(v=vs.94).aspx</a></li></ul>
<p>The Requirements section on MSDN were dropped.
</p><p>Add them to the Import Notes section.
</p>
<h3><span class="mw-headline" id="Review_all_content_in_.22Main_content.22_field">Review all content in "Main content" field</span></h3>
<p>If there are any constructor, properties, functions, or methods lists, compare them to the automatically generated one. Delete duplicates from the "Main content" field.
</p><p>This "Main content" field will be removed after our review. Move any remaining content out of this field and to either Usage, Notes, or Import Notes.
</p>
<h3><span class="mw-headline" id="Compare_the_syntax_values_to_the_ones_in_the_specification">Compare the syntax values to the ones in the specification</span></h3>
<p>Make sure all syntax variations are reflected.
</p><p>Example:
</p>
<ul><li> <a rel="nofollow" class="external free" href="http://docs.webplatform.org/wiki/javascript/Array">http://docs.webplatform.org/wiki/javascript/Array</a></li>
<li> <a rel="nofollow" class="external free" href="http://www.ecma-international.org/ecma-262/5.1/#sec-15.4">http://www.ecma-international.org/ecma-262/5.1/#sec-15.4</a></li></ul>
<p>Under Section 15.4 of the spec:
</p>
<ul><li> the first syntax variation is when the Array Constructor is called as a function (15.4.1):
<ul><li> <code>[ item1 [ , item2 [ , … ] ] ]</code></li></ul></li>
<li> the second variation is when the Array Constructor is called as part of a "new" expression (15.4.2). This variation takes 2 different kinds of parameters: items (15.4.2.1) and length (15.4.2.1), so show both:
<ul><li> <code>new Array ( [ item0 [ , item1 [ , … ] ] ] )</code></li>
<li> <code>new Array (len)</code></li></ul></li></ul>
<h3><span class="mw-headline" id="Remove_lefthand_assignment_from_the_parameters_list">Remove lefthand assignment from the parameters list</span></h3>
<p>For example:
</p>
<ul><li> <a rel="nofollow" class="external free" href="http://docs.webplatform.org/wiki/javascript/Array">http://docs.webplatform.org/wiki/javascript/Array</a></li>
<li> <a rel="nofollow" class="external free" href="http://msdn.microsoft.com/en-us/library/ie/k4h76zbx(v=vs.94).aspx">http://msdn.microsoft.com/en-us/library/ie/k4h76zbx(v=vs.94).aspx</a></li></ul>
<p><code>arrayObj</code> is not a parameter of the Array Object. 
</p><p>If the description for that lefthand assignment provides additional information, such as what is returned, move that information to another, more appropriate, section.
</p><p>Then, remove <code>arrayObj</code> from the list of parameters.
</p><p>Move any return values to the Return Value section
</p>
<h3><span class="mw-headline" id="Add_the_specification_to_the_WPD_page">Add the specification to the WPD page</span></h3>
<p>In the Manual sections, add a link to the spec
</p><p>For example:
</p>
<pre>
===Specification===
[http://www.ecma-international.org/ecma-262/5.1/#sec-15.4 15.4 Array Objects]
ECMAScript® Language Specification
Standard ECMA-262
5.1 Edition / June 2011
</pre>
<h3><span class="mw-headline" id="Add_the_page_type_to_the_WPD_page">Add the page type to the WPD page</span></h3>
<p>In the form edit view, in the JavaScript Page section, select the page type.
</p><p>For example, the Array page:
</p><p><a rel="nofollow" class="external free" href="http://docs.webplatform.org/w/index.php?title=javascript/Array&amp;action=formedit">http://docs.webplatform.org/w/index.php?title=javascript/Array&amp;action=formedit</a>
</p><p>Is a JS Object page
</p>
<!-- 
NewPP limit report
CPU time usage: 0.017 seconds
Real time usage: 0.018 seconds
Preprocessor visited node count: 31/1000000
Preprocessor generated node count: 48/1000000
Post‐expand include size: 0/2097152 bytes
Template argument size: 0/2097152 bytes
Highest expansion depth: 2/40
Expensive parser function count: 0/100
-->

<!-- 
Transclusion expansion time report (%,ms,calls,template)
100.00%    0.000      1 - -total
-->

<!-- Saved in parser cache with key wpwiki:pcache:idhash:16141-0!*!*!!*!*!*!esi=1 and timestamp 20150731094108 and revision id 46939
 -->
