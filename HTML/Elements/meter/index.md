---
title: Meta:HTML/Elements/meter
---
<h1><span class="mw-headline" id="meter">meter</span></h1>
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
<div style="float: right;background: white;border:1px dashed black;padding: 1ex;margin-left:1ex;">
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">List of Elements</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">Forms</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements/form&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/form (page does not exist)">form</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/fieldset&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/fieldset (page does not exist)">fieldset</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/legend&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/legend (page does not exist)">legend</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/label&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/label (page does not exist)">label</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/input&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/input (page does not exist)">input</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/button&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/button (page does not exist)">button</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/select&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/select (page does not exist)">select</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/datalist&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/datalist (page does not exist)">datalist</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/optgroup&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/optgroup (page does not exist)">optgroup</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/option&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/option (page does not exist)">option</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/textarea&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/textarea (page does not exist)">textarea</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/keygen&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/keygen (page does not exist)">keygen</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/output&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/output (page does not exist)">output</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/progress&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/progress (page does not exist)">progress</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/meter&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/meter (page does not exist)">meter</a></li></ul></li></ul></li></ul>
</div>
<h1><span class="mw-headline" id=".3Cmeter.3E">&lt;meter&gt;</span></h1>
<p>The &lt;meter&gt; element represents a scalar measurement within a known range, or a fractional value.
</p>
<h2><span class="mw-headline" id="Point">Point</span></h2>
<ul><li>Example of meter:
<ul><li>disk usage</li>
<li>relevance of a query result</li>
<li>fraction of a voting population to have selected a particular candidate ...</li></ul></li></ul>
<p><br />
</p>
<ul><li>The meter element should not be used to indicate progress (as in a progress bar). For that role, HTML provides a separate progress element.</li></ul>
<p><br />
</p>
<ul><li>The meter element also does not represent a scalar value of arbitrary range — for example, it would be wrong to use this to report a weight, or height, unless there is a known maximum value. <a href="#Example_of_bad_usage">[Example of bad usage]</a></li></ul>
<p><br />
</p>
<ul><li>Authors are encouraged to include a textual representation of the gauge's state in the element's contents, for users of user agents that do not support the meter element.</li></ul>
<h2><span class="mw-headline" id="HTML_Attributes">HTML Attributes</span></h2>
<ul><li><code>value</code> = valid floating point numbers<br />Specifies the value to have the gauge indicate as the "measured" value.<br />The value attribute must be specified.</li></ul>
<p><br />
</p>
<ul><li><code>min</code> = valid floating point numbers<br />Specifies the lower bound of the range.</li></ul>
<p><br />
</p>
<ul><li><code>max</code> = valid floating point numbers<br />Specifies the upper bound</li></ul>
<p><br />
</p>
<ul><li><code>low</code> = valid floating point numbers<br />Specifies the range that is considered to be the "low" part.</li></ul>
<p><br />
</p>
<ul><li><code>high</code> = valid floating point numbers<br />Specifies the range that is considered to be the "high" part.</li></ul>
<p><br />
</p>
<ul><li><code>optimum</code> = valid floating point numbers<br />Gives the position that is "optimum":
<ul><li>If that is higher than the "high" value then this indicates that the higher the value, the better</li>
<li>if it's lower than the "low" mark then it indicates that lower values are better</li>
<li>if it is in between then it indicates that neither high nor low values are good.</li></ul></li></ul>
<p><br />
See also <a href="/w/index.php?title=HTML/Attributes/_Global&amp;action=edit&amp;redlink=1" class="new" title="HTML/Attributes/ Global (page does not exist)">global attributes</a>.
</p><p><br />
</p>
<h2><span class="mw-headline" id="Examples">Examples</span></h2>
<h3><span class="mw-headline" id="Example_A">Example A</span></h3>
<p>The following examples show three gauges that would all be three-quarters full [try it]:
</p>
<pre>
Storage space usage: &lt;meter value=6 max=8&gt;6 blocks used (out of 8 total)&lt;/meter&gt;
Voter turnout: &lt;meter value=0.75&gt;&lt;img alt=&quot;75%&quot; src=&quot;graph75.png&quot;&gt;&lt;/meter&gt;
Tickets sold: &lt;meter min=&quot;0&quot; max=&quot;100&quot; value=&quot;75&quot;&gt;&lt;/meter&gt;
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Meter01.png" class="new" title="File:Meter01.png">File:Meter01.png</a>
</p>
<h3><span class="mw-headline" id="Example_B">Example B</span></h3>
<p>There is no explicit way to specify units in the meter element, but the units may be specified in the title attribute in free-form text [try it]:
</p>
<pre>
&lt;dl&gt;
  &lt;dt&gt;Radius: &lt;dd&gt; &lt;meter min=0 max=20 value=12 title=&quot;centimeters&quot;&gt;12cm&lt;/meter&gt;
  &lt;dt&gt;Height: &lt;dd&gt; &lt;meter min=0 max=10 value=2 title=&quot;centimeters&quot;&gt;2cm&lt;/meter&gt;
&lt;/dl&gt;
</pre>
<p><br />
</p>
<h3><span class="mw-headline" id="Example_of_bad_usage"><span style="color:#9c0037;">Example of bad usage</span></span></h3>
<p>The following example is incorrect use of the element, because it doesn't give a range (and since the default maximum is 1, both of the gauges would end up looking maxed out)
</p>
<pre style="color:gray;">
&lt;!-- do not copy this example, it is an example of bad usage! --&gt;
&lt;p&gt;The grapefruit pie had a radius of &lt;meter value=12&gt;12cm&lt;/meter&gt;
and a height of &lt;meter value=2&gt;2cm&lt;/meter&gt;.&lt;/p&gt;
</pre> 
<p><br />
</p>
<h2><span class="mw-headline" id="HTML_Reference">HTML Reference</span></h2>
<p>The HTML5 specification defines the &lt;meter&gt; element in <a rel="nofollow" class="external text" href="http://www.w3.org/TR/html5/the-button-element.html#the-meter-element">4.10.17 The meter element</a>.
</p>
<div class="editors-only">
<p><b>Needs Examples</b>:  This section should include examples. 
</p>
</div>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>

<!-- Saved in parser cache with key wpwiki:pcache:idhash:922-0!*!0!!*!5!*!esi=1 and timestamp 20150731181605 and revision id 12678
 -->
