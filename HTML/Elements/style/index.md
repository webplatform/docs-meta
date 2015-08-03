---
title: Meta:HTML/Elements/style
---
<h1><span class="mw-headline" id="style">style</span></h1>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>Style element contains style information for a document. Style information should go inside of this element, usually in the <a href="/wiki/css" title="css">CSS</a> language.
</p><p><br />
</p>
<h2><span class="mw-headline" id="Overview_Table">Overview Table</span></h2>
<table class="wikitable">
<tr>
<th> <a href="/wiki/dom/interface" title="dom/interface"> DOM Interface</a>
</th>
<td> <a href="/wiki/dom/HTMLStyleElement" title="dom/HTMLStyleElement">HTMLStyleElement</a>
</td></tr></table>
<div class="editors-only">
<p><b>Merge Candidate</b>:  This page is a candidate for merge with the following pages: <a href="/wiki/html/elements/style" title="html/elements/style">html/elements/style</a> 
</p>
</div>
<p><br />
</p>
<div style="float: right;background: white;border:1px dashed black;padding: 1ex;margin-left: 1ex;">
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">List of Elements</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">Document metadata</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements/head&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/head (page does not exist)">head</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/title&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/title (page does not exist)">title</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/base&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/base (page does not exist)">base</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/isindex&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/isindex (page does not exist)">isindex</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/link&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/link (page does not exist)">link</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/meta&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/meta (page does not exist)">meta</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/style&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/style (page does not exist)">style</a></li></ul></li></ul></li></ul>
</div>
<h1><span class="mw-headline" id=".3Cstyle.3E">&lt;style&gt;</span></h1>
<p>The &lt;style&gt; element allows authors to embed style information in their documents.
</p><p><br />
</p>
<h2><span class="mw-headline" id="HTML_Attributes">HTML Attributes</span></h2>
<ul><li><code>media</code> = media-query list<br />Specifies which media the styles apply to.<br />The default, if the media attribute is omitted, is "all", meaning that by default styles apply to all media.</li></ul>
<p><br />
</p>
<ul><li><code>type</code> = A valid MIME type that designates a styling language.<br />Gives the styling language.<br />The default value for the type attribute, which is used if the attribute is absent, is "text/css".</li></ul>
<p><br />
</p>
<ul><li><code>scoped</code> = boolean<br />Indicates that the specified style information is meant to apply only to the style element’s parent element, and that element’s child nodes. Otherwise, the specified styles are meant to apply to the entire document. <a href="#Example_B">[Example B]</a></li></ul>
<p><br />
</p>
<ul><li>Also, the title attribute has special semantics on this element.<br />The title attribute on style elements defines alternative style sheet sets. If the style element has no title attribute, then it has no title; the title attribute of ancestors does not apply to the style element.</li></ul>
<p><br />
See also <a href="/w/index.php?title=HTML/Attributes/_Global&amp;action=edit&amp;redlink=1" class="new" title="HTML/Attributes/ Global (page does not exist)">global attributes</a>.
</p><p><br />
</p>
<h2><span class="mw-headline" id="Example">Example</span></h2>
<h3><span class="mw-headline" id="Example_A">Example A</span></h3>
<p>The following document has its emphasis styled as bright red text rather than italics text, while leaving titles of works and Latin words in their default italics. It shows how using appropriate elements enables easier restyling of documents. [try it]:
</p>
<pre>
&lt;!DOCTYPE html&gt;
&lt;html lang=&quot;en&quot;&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;utf-8&quot;&gt;
    &lt;title&gt;My favorite book&lt;/title&gt;
    &lt;style&gt;
       body { color: black; background: white; }
       em { font-style: normal; color: red; }
    &lt;/style&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;p&gt;My &lt;em&gt;favorite&lt;/em&gt; book of all time has &lt;em&gt;got&lt;/em&gt; to be
    &lt;cite&gt;A Cat's Life&lt;/cite&gt;. It is a book by P. Rahmel that talks
    about the &lt;i lang=&quot;la&quot;&gt;Felis Catus&lt;/i&gt; in modern human society.&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Style01.png" class="new" title="File:Style01.png">File:Style01.png</a>
</p>
<h3><span class="mw-headline" id="Example_B">Example B</span></h3>
<p>In the following example, the style element influences only a p element in section element. [try it]:
</p>
<pre>
&lt;p&gt;text&lt;/p&gt;
&lt;section id=&quot;example1&quot;&gt;
  &lt;style scoped=&quot;scoped&quot;&gt;
    p {
      color: #ff0000;
    }
  &lt;/style&gt;
  &lt;h1&gt;title&lt;/h1&gt;
  &lt;p&gt;text&lt;/p&gt;
&lt;/section&gt;
</pre>
<p>The following example is use to present markup to user agents that don't support the scoped attribute. [try it]:
</p>
<pre>
&lt;p&gt;text&lt;/p&gt;
&lt;section id=&quot;example1&quot;&gt;
  &lt;style scoped=&quot;scoped&quot;&gt;
    #example1 p {
      color: #ff0000;
    }
  &lt;/style&gt;
  &lt;h1&gt;title&lt;/h1&gt;
  &lt;p&gt;text&lt;/p&gt;
&lt;/section&gt;
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Style03.png" class="new" title="File:Style03.png">File:Style03.png</a>
</p>
<h2><span class="mw-headline" id="HTML_Reference">HTML Reference</span></h2>
<p>The HTML5 specification defines the &lt;style&gt; element in <a rel="nofollow" class="external text" href="http://www.w3.org/TR/html5/semantics.html#the-style-element">4.2.6 The style element</a>.
</p>
<div class="editors-only">
<p><b>Needs Examples</b>:  This section should include examples. 
</p>
</div>
<div class="attribution">
<h2><span class="mw-headline" id="Attribution">Attribution</span></h2>
<p><i>This article contains content originally from external sources.</i>
</p>
<div class="attribution-block">
Portions of this content come from the Mozilla Developer Network <div class="MediaTransformError" style="width: 120px; height: 23px; display:inline-block;">Error creating thumbnail: File missing</div>: <a rel="nofollow" class="external text" href="https://developer.mozilla.org/en-US/docs/HTML/Element/style">Article</a>
</div>
</div>

<!-- 
NewPP limit report
CPU time usage: 0.176 seconds
Real time usage: 1.440 seconds
Preprocessor visited node count: 268/1000000
Preprocessor generated node count: 2014/1000000
Post‐expand include size: 6117/2097152 bytes
Template argument size: 3801/2097152 bytes
Highest expansion depth: 9/40
Expensive parser function count: 0/100
-->

<!-- 
Transclusion expansion time report (%,ms,calls,template)
100.00%  124.109      1 - -total
 20.20%   25.070      1 - Template:Markup_Element
 17.61%   21.856      1 - Template:External_Attribution
 11.79%   14.628      1 - Template:Page_Title
  8.91%   11.057      1 - Template:Editorial/Merge_Candidate
  8.73%   10.837      1 - Template:Flags
  8.19%   10.162      1 - Template:Examples_Section
  7.02%    8.707      1 - Template:External_Attribution_Block/MDN
  6.53%    8.101      2 - Template:Editorial
  5.73%    7.116      1 - Template:API_Name
-->

<!-- Saved in parser cache with key wpwiki:pcache:idhash:809-0!*!0!!*!5!*!esi=1 and timestamp 20150731134337 and revision id 13372
 -->
