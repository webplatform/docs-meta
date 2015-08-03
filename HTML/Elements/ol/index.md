---
title: Meta:HTML/Elements/ol
---
<h1><span class="mw-headline" id="ol">ol</span></h1>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>The ol element makes an <i>ordered list</i> from the li (<i>list item</i>) elements it contains. Typically, each item is rendered with a number before it.
</p><p><br />
</p>
<h2><span class="mw-headline" id="Overview_Table">Overview Table</span></h2>
<table class="wikitable">
<tr>
<th> <a href="/wiki/dom/interface" title="dom/interface"> DOM Interface</a>
</th>
<td> <a href="/w/index.php?title=%3F&amp;action=edit&amp;redlink=1" class="new" title="? (page does not exist)">?</a>
</td></tr></table>
<div style="float: right;background: white;border:1px dashed black;padding: 1ex;margin-left: 1ex;">
<ul><li> <a href="/wiki/Meta:HTML/Elements" title="Meta:HTML/Elements">List of Elements</a>
<ul><li> <a href="/wiki/Meta:HTML/Elements#Grouping_content" title="Meta:HTML/Elements">Grouping content</a>
<ul><li> <a href="/wiki/Meta:HTML/Elements/p" title="Meta:HTML/Elements/p" class="mw-redirect">p</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/hr" title="Meta:HTML/Elements/hr" class="mw-redirect">hr</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/pre" title="Meta:HTML/Elements/pre" class="mw-redirect">pre</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/blockquote" title="Meta:HTML/Elements/blockquote" class="mw-redirect">blockquote</a></li>
<li> <strong class="selflink">ol</strong></li>
<li> <a href="/wiki/Meta:HTML/Elements/ul" title="Meta:HTML/Elements/ul" class="mw-redirect">ul</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/li" title="Meta:HTML/Elements/li" class="mw-redirect">li</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/dl" title="Meta:HTML/Elements/dl" class="mw-redirect">dl</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/dt" title="Meta:HTML/Elements/dt" class="mw-redirect">dt</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/dd" title="Meta:HTML/Elements/dd" class="mw-redirect">dd</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/figure" title="Meta:HTML/Elements/figure" class="mw-redirect">figure</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/figcaption" title="Meta:HTML/Elements/figcaption" class="mw-redirect">figcaption</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/div" title="Meta:HTML/Elements/div" class="mw-redirect">div</a></li>
<li> <a href="/wiki/Meta:HTML/Elements/center" title="Meta:HTML/Elements/center" class="mw-redirect">center</a></li></ul></li></ul></li></ul>
</div>
<h1><span class="mw-headline" id=".3Col.3E">&lt;ol&gt;</span></h1>
<p>The &lt;ol&gt; element represents an <i>ordered list</i>. By default, most browsers add an integer as a marker before each list item:
</p>
<ol><li> First list item</li>
<li> Second list item</li>
<li> Third list item</li></ol>
<p><a href="#Example_A">[Example A]</a>
</p><p>Use an ordered list where there's meaning to the order in which the list items appear. If the order is not important, it is more appropriate to use a <a href="/wiki/Meta:HTML/Elements/ul" title="Meta:HTML/Elements/ul" class="mw-redirect">&lt;ul&gt;</a> unordered list element.
</p>
<h2><span class="mw-headline" id="HTML_Attributes">HTML Attributes</span></h2>
<ul><li> <code>reversed</code><br />Renders numbers for the items in descending order list (...3, 2, 1), instead of the default ascending order (1, 2, 3...). <a href="#Example_B">[Example B]</a></li></ul>
<p><br />
</p>
<ul><li> <code>start</code> = valid integer<br />Specifies the value for the first list item. <a href="#Example_C">[Example C]</a></li></ul>
<p><br />
</p>
<ul><li> <code>type</code> = the kind of marker<br />Specifies the kind of marker to use in the list. <a href="#Example_D">[Example D]</a></li></ul>
<table class="wikitable">
    <tr>
      <th>
<pre>       Value
</pre>
      </th>
      <th>
<pre>       Marker type
</pre>
      </th>
    </tr>
    <tr>
      <td>
<pre>       1
</pre>
      </td>
      <td>
<pre>       <i>Default value</i> Arabic numerals (1, 2, 3, 4)
</pre>
      </td>
    </tr>
    <tr>
      <td>
<pre>       a
</pre>
      </td>
      <td>
<pre>       Lowercase roman letters in alphabetical ordered (a, b, c, d)
</pre>
      </td>
    </tr>
    <tr>
      <td>
<pre>       A
</pre>
      </td>
      <td>
<pre>       Uppercase roman letters in alphabetical order (A, B, C, D)
</pre>
      </td>
    </tr>
    <tr>
      <td>
<pre>       i
</pre>
      </td>
      <td>
<pre>       Lowercase roman numerals numbers, lowercase (i, ii, iii, iv)
</pre>
      </td>
    </tr>
    <tr>
      <td>
<pre>       I
</pre>
      </td>
      <td>
<pre>       Uppercase roman numerals numbers, lowercase (I, II, III, IV)
</pre>
      </td>
    </tr>
</table>
<p><br />
See also <a href="/w/index.php?title=HTML/Attributes/_Global&amp;action=edit&amp;redlink=1" class="new" title="HTML/Attributes/ Global (page does not exist)">global attributes</a>.
</p>
<h2><span class="mw-headline" id="Examples">Examples</span></h2>
<h3><span class="mw-headline" id="Example_A">Example A</span></h3>
<p>[try it]
</p>
<pre>
&lt;ol&gt;
  &lt;li&gt;sample1&lt;/li&gt;
  &lt;li&gt;sample2&lt;/li&gt;
  &lt;li&gt;sample3&lt;/li&gt;
&lt;/ol&gt;
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Ol01.png" class="new" title="File:Ol01.png">File:Ol01.png</a>
</p>
<h3><span class="mw-headline" id="Example_B">Example B</span></h3>
<p>With the reversed attribute [try it]:
</p>
<pre>
&lt;ol reversed&gt;
  &lt;li&gt;sample1&lt;/li&gt;
  &lt;li&gt;sample2&lt;/li&gt;
  &lt;li&gt;sample3&lt;/li&gt;
&lt;/ol&gt; 
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Li02.png" class="new" title="File:Li02.png">File:Li02.png</a>
</p>
<h3><span class="mw-headline" id="Example_C">Example C</span></h3>
<p>With the start attribute [try it]:
</p>
<pre>
&lt;ol start=&quot;101&quot;&gt;
  &lt;li&gt;sample1&lt;/li&gt;
  &lt;li&gt;sample2&lt;/li&gt;
  &lt;li&gt;sample3&lt;/li&gt;
&lt;/ol&gt; 
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Ol03.png" class="new" title="File:Ol03.png">File:Ol03.png</a>
</p>
<h3><span class="mw-headline" id="Example_D">Example D</span></h3>
<p>With the type attribute [try it]:
</p>
<pre>
&lt;ol type=&quot;lower-alpha&quot;&gt;
  &lt;li&gt;sample1&lt;/li&gt;
  &lt;li&gt;sample2&lt;/li&gt;
  &lt;li&gt;sample3&lt;/li&gt;
&lt;/ol&gt; 
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Ol04.png" class="new" title="File:Ol04.png">File:Ol04.png</a>
</p>
<h2><span class="mw-headline" id="HTML_Reference">HTML Reference</span></h2>
<p>The HTML5 specification defines the &lt;ol&gt; element in <a rel="nofollow" class="external text" href="http://www.w3.org/TR/html5/grouping-content.html#the-ol-element">4.5.5 The ol element</a>.
</p>
<h2><span class="mw-headline" id="See_also">See also</span></h2>
<ul><li> <a href="/wiki/guides/html_lists" title="guides/html lists">HTML Lists</a></li></ul>
<div class="editors-only">
<p><b>Needs Examples</b>:  This section should include examples. 
</p>
</div>
<p><br />
</p><p><br />
</p><p><br />
</p>
<h2><span class="mw-headline" id="See_also_2">See also</span></h2>
<h3><span class="mw-headline" id="Related_articles">Related articles</span></h3>
<h4><span class="mw-headline" id="HTML">HTML</span></h4>
<ul><li> <a href="/wiki/css/properties/user-modify" title="css/properties/user-modify">user-modify</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/dom/HTMLAudioElement" title="dom/HTMLAudioElement">HTMLAudioElement</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/dom/HTMLTextAreaElement/textLength" title="dom/HTMLTextAreaElement/textLength">textLength</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/dom/HTMLTextAreaElement/value" title="dom/HTMLTextAreaElement/value">value</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/accept" title="html/attributes/accept">accept</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/action" title="html/attributes/action">action</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/alt" title="html/attributes/alt">alt</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/autocomplete" title="html/attributes/autocomplete">autocomplete</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/autofocus" title="html/attributes/autofocus">autofocus</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/checked" title="html/attributes/checked">checked</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/crossorigin" title="html/attributes/crossorigin">crossorigin</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/form" title="html/attributes/form">form</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/formEnctype" title="html/attributes/formEnctype">formEnctype</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/height" title="html/attributes/height">height</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/list" title="html/attributes/list">list</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/max_(HTMLInputElement)" title="html/attributes/max (HTMLInputElement)">max (HTMLInputElement)</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/maxLength" title="html/attributes/maxLength">maxLength</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/min" title="html/attributes/min">min</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/multiple" title="html/attributes/multiple">multiple</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/readonly" title="html/attributes/readonly">readonly</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/size" title="html/attributes/size">size</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/standby" title="html/attributes/standby">standby</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/attributes/step" title="html/attributes/step">step</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/!DOCTYPE" title="html/elements/!DOCTYPE">!DOCTYPE</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/!DOCTYPE/ja" title="html/elements/!DOCTYPE/ja">!DOCTYPE</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/acronym" title="html/elements/acronym">acronym</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/b" title="html/elements/b">b</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/b/ja" title="html/elements/b/ja">b</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/br" title="html/elements/br">br</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/button" title="html/elements/button">button</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/caption" title="html/elements/caption">caption</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/cite" title="html/elements/cite">cite</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/code" title="html/elements/code">code</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/col" title="html/elements/col">col</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/colgroup" title="html/elements/colgroup">colgroup</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/datalist" title="html/elements/datalist">datalist</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/del" title="html/elements/del">del</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/dfn" title="html/elements/dfn">dfn</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/div" title="html/elements/div">div</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/em" title="html/elements/em">em</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/embed" title="html/elements/embed">EMBED</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/fieldset" title="html/elements/fieldset">fieldset</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/font" title="html/elements/font">font</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/footer" title="html/elements/footer">footer</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/head" title="html/elements/head">head</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/hn" title="html/elements/hn">hn</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/hr" title="html/elements/hr">hr</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/html" title="html/elements/html">html</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/i" title="html/elements/i">i</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/html/elements/img" title="html/elements/img">img</a></li></ul>
<pre><a href="/wiki/Special:Ask/-5B-5BTopic_Cluster::HTML-5D-5D/-3FPage-20Title/format%3Dtemplate/link%3Dnone/template%3DSee_Also_Item/offset%3D50" title="Special:Ask/-5B-5BTopic Cluster::HTML-5D-5D/-3FPage-20Title/format=template/link=none/template=See Also Item/offset=50">… further results</a>
</pre>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>

<!-- Saved in parser cache with key wpwiki:pcache:idhash:824-0!*!0!!*!5!*!esi=1 and timestamp 20150731181441 and revision id 29050
 -->
