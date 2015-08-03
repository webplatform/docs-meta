---
title: Meta:HTML/Elements/optgroup
---
<h1><span class="mw-headline" id="optgroup">optgroup</span></h1>
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
<h1><span class="mw-headline" id=".3Coptgroup.3E">&lt;optgroup&gt;</span></h1>
<p>The &lt;optgroup&gt; element represents a group of option elements with a common label.
</p>
<h2><span class="mw-headline" id="Point">Point</span></h2>
<ul><li>The label attribute must be specified. <a href="#Example_A">[Example A]</a></li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="HTML_Attributes">HTML Attributes</span></h2>
<ul><li><code>disabled</code> = boolean<br />if present, disable a group of option elements together.</li></ul>
<p><br />
</p>
<ul><li><code>label</code> = string<br />Its value gives the name of the group, for the purposes of the user interface.</li></ul>
<p><br />
See <a href="/w/index.php?title=HTML/Attributes/_Global&amp;action=edit&amp;redlink=1" class="new" title="HTML/Attributes/ Global (page does not exist)">global attributes</a>.
</p><p><br />
</p>
<h2><span class="mw-headline" id="Examples">Examples</span></h2>
<h3><span class="mw-headline" id="Example_A">Example A</span></h3>
<p>[try it]:
</p>
<pre>
&lt;form action=&quot;courseselector.dll&quot; method=&quot;get&quot;&gt;
  &lt;p&gt;Which course would you like to watch today?
  &lt;p&gt;&lt;label&gt;Course:
    &lt;select name=&quot;c&quot;&gt;
      &lt;optgroup label=&quot;8.01 Physics I: Classical Mechanics&quot;&gt;
        &lt;option value=&quot;8.01.1&quot;&gt;Lecture 01: Powers of Ten&lt;/option&gt;
        &lt;option value=&quot;8.01.2&quot;&gt;Lecture 02: 1D Kinematics&lt;/option&gt;
        &lt;option value=&quot;8.01.3&quot;&gt;Lecture 03: Vectors&lt;/option&gt;
      &lt;/optgroup&gt;
      &lt;optgroup label=&quot;8.02 Electricity and Magnestism&quot;&gt;
        &lt;option value=&quot;8.02.1&quot;&gt;Lecture 01: What holds our world together?&lt;/option&gt;
        &lt;option value=&quot;8.02.2&quot;&gt;Lecture 02: Electric Field&lt;/option&gt;
        &lt;option value=&quot;8.02.3&quot;&gt;Lecture 03: Electric Flux&lt;/option&gt;
      &lt;/optgroup&gt;
      &lt;optgroup label=&quot;8.03 Physics III: Vibrations and Waves&quot;&gt;
        &lt;option value=&quot;8.03.1&quot;&gt;Lecture 01: Periodic Phenomenon&lt;/option&gt;
        &lt;option value=&quot;8.03.2&quot;&gt;Lecture 02: Beats&lt;/option&gt;
        &lt;option value=&quot;8.03.3&quot;&gt;Lecture 03: Forced Oscillations with Damping&lt;/option&gt;
      &lt;/optgroup&gt;
    &lt;/select&gt;
  &lt;/label&gt;
  &lt;p&gt;&lt;input type=submit value=&quot;▶ Play&quot;&gt;
&lt;/form&gt;
</pre>
<h2><span class="mw-headline" id="HTML_Reference">HTML Reference</span></h2>
<p>The HTML5 specification defines the &lt;optgroup&gt; element in <a rel="nofollow" class="external text" href="http://www.w3.org/TR/html5/the-button-element.html#the-optgroup-element">4.10.11 The optgroup element</a>.
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

<!-- Saved in parser cache with key wpwiki:pcache:idhash:916-0!*!0!!*!*!*!esi=1 and timestamp 20150731181555 and revision id 5670
 -->
