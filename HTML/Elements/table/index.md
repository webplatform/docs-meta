---
title: Meta:HTML/Elements/table
---
<h1><span class="mw-headline" id="table">table</span></h1>
<div class="editors-only">
<p><b>Needs Summary</b>:   This article does not have a summary. Summaries give a brief overview of the topic and are automatically included on some listing pages that link to this article. 
</p>
</div>
<p><br />
</p>
<h2><span class="mw-headline" id="Overview_Table">Overview Table</span></h2>
<table class="wikitable">
<tr>
<th> <a href="/wiki/dom/interface" title="dom/interface"> DOM Interface</a>
</th>
<td> <a href="/w/index.php?title=%3F&amp;action=edit&amp;redlink=1" class="new" title="? (page does not exist)">?</a>
</td></tr></table>
<div style="float: right;background: white;border:1px dashed black;padding: 1ex;margin-left: 1ex;">
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">List of Elements</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">Tables</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements/table&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/table (page does not exist)">table</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/caption&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/caption (page does not exist)">caption</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/colgroup&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/colgroup (page does not exist)">colgroup</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/col&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/col (page does not exist)">col</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/tbody&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/tbody (page does not exist)">tbody</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/thead&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/thead (page does not exist)">thead</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/tfoot&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/tfoot (page does not exist)">tfoot</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/tr&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/tr (page does not exist)">tr</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/td&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/td (page does not exist)">td</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/th&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/th (page does not exist)">th</a></li></ul></li></ul></li></ul>
</div>
<h1><span class="mw-headline" id=".3Ctable.3E">&lt;table&gt;</span></h1>
<p>The &lt;table&gt; element represents data with more than one dimension, in the form of a table.
</p>
<h2><span class="mw-headline" id="Point">Point</span></h2>
<ul><li>Tables must not be used as layout aids. There are a variety of alternatives to using HTML tables for layout, primarily using CSS positioning and the CSS table model.</li>
<li>Users might have difficulty understanding the content, authors should include explanatory information introducing the table. This information is useful for all users, but is especially useful for users who cannot see the table, e.g. users of screen readers.<a href="#Example_B">[Example B]</a></li>
<li>Tables have rows and columns given by their descendants. A table must not have an empty row or column. </li></ul>
<h2><span class="mw-headline" id="HTML_Attributes">HTML Attributes</span></h2>
<ul><li><code>summary</code> = explanatory information introducing the table</li></ul>
<p>See also <a href="/w/index.php?title=HTML/Attributes/_Global&amp;action=edit&amp;redlink=1" class="new" title="HTML/Attributes/ Global (page does not exist)">global attributes</a>.
</p>
<h2><span class="mw-headline" id="Examples">Examples</span></h2>
<h3><span class="mw-headline" id="Example_A">Example A</span></h3>
<p>[try it]:
</p>
<pre>
&lt;table&gt;
  &lt;caption&gt;Characteristics with positive and negative sides&lt;/caption&gt;
  &lt;thead&gt;
    &lt;tr&gt;
      &lt;th&gt;Characteristic&lt;/th&gt;
      &lt;th&gt;Negative&lt;/th&gt;
      &lt;th&gt;Positive&lt;/th&gt;
    &lt;/tr&gt;
  &lt;/thead&gt;
  &lt;tbody&gt;
    &lt;tr&gt;
      &lt;th&gt;Mood&lt;/th&gt;
      &lt;td&gt;Sad&lt;/td&gt;
      &lt;td&gt;Happy&lt;/td&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
      &lt;th&gt;Grade&lt;/th&gt;
      &lt;td&gt;Failing&lt;/td&gt;
      &lt;td&gt;Passing&lt;/td&gt;
    &lt;/tr&gt;
  &lt;/tbody&gt;
&lt;/table&gt;
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Table01.png" class="new" title="File:Table01.png">File:Table01.png</a>
</p>
<h3><span class="mw-headline" id="Example_B">Example B</span></h3>
<p>The following example is including explanatory information introducing the table by next to the table in the same figure [try it]:
</p>
<pre>
&lt;figure&gt;
  &lt;figcaption&gt;Characteristics with positive and negative sides&lt;/figcaption&gt;
  &lt;p&gt;Characteristics are given in the second column, with the
  negative side in the left column and the positive side in the right column.&lt;/p&gt;
  &lt;table&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th id=&quot;n&quot;&gt;Negative&lt;/th&gt;
        &lt;th&gt;Characteristic&lt;/th&gt;
        &lt;th id=&quot;p&quot;&gt;Positive&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;tr&gt;
        &lt;td headers=&quot;n r1&quot;&gt;Sad&lt;/td&gt;
        &lt;th id=&quot;r1&quot;&gt;Mood&lt;/th&gt;
        &lt;td headers=&quot;p r1&quot;&gt;Happy&lt;/td&gt;
      &lt;/tr&gt;
      &lt;tr&gt;
        &lt;td headers=&quot;n r2&quot;&gt;Failing&lt;/td&gt;
        &lt;th id=&quot;r2&quot;&gt;Grade&lt;/th&gt;
        &lt;td headers=&quot;p r2&quot;&gt;Passing&lt;/td&gt;
      &lt;/tr&gt;
    &lt;/tbody&gt;
   &lt;/table&gt;
&lt;/figure&gt;
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Table02.png" class="new" title="File:Table02.png">File:Table02.png</a>
</p>
<h2><span class="mw-headline" id="HTML_Reference">HTML Reference</span></h2>
<p>The HTML5 specification defines the &lt;table&gt; element in <a rel="nofollow" class="external text" href="http://www.w3.org/TR/html5/tabular-data.html#the-table-element">4.9.1 The table element</a>.
</p>
<h2><span class="mw-headline" id="See_also">See also</span></h2>
<ul><li> <a href="/w/index.php?title=HTML_tables&amp;action=edit&amp;redlink=1" class="new" title="HTML tables (page does not exist)">HTML tables</a></li></ul>
<div class="editors-only">
<p><b>Needs Examples</b>:  This section should include examples. 
</p>
</div>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>

<!-- Saved in parser cache with key wpwiki:pcache:idhash:898-0!*!0!!*!5!*!esi=1 and timestamp 20150731181534 and revision id 5622
 -->
