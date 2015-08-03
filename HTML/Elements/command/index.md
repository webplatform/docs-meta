---
title: Meta:HTML/Elements/command
---
<h1><span class="mw-headline" id="command">command</span></h1>
<p><span class="standardization_status" title="Experimental">Experimental</span>
</p>
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
<td> [[|]]
</td></tr></table>
<h1><span class="mw-headline" id=".3Ccommand.3E">&lt;command&gt;</span></h1>
<p>The &lt;command&gt; element represents a command that the user can invoke.
</p>
<h2><span class="mw-headline" id="Point">Point</span></h2>
<ul><li>A command can be part of a context menu or toolbar, using the menu element, or can be put anywhere else in the page, to define a keyboard shortcut.</li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="HTML_Attributes">HTML Attributes</span></h2>
<ul><li><code>type</code> = command/ checkbox/ radio<br />Indicates the kind of command:
<ul><li>command<br />Normal command with an associated action.</li>
<li>checkbox<br />State or option that can be toggled.</li>
<li>radio<br />Selection of one item from a list of items.</li></ul></li></ul>
<p><br />
</p>
<ul><li><code>label</code> = string<br />Gives the name of the command, as shown to the user.<br />The label attribute must be specified and must have a value that is not the empty string.</li></ul>
<p><br />
</p>
<ul><li><code>icon</code> = valid non-empty URL potentially<br />Gives a picture that represents the command.</li></ul>
<p><br />
</p>
<ul><li><code>disabled</code> = boolean<br />If present, indicates that the command is not available in the current state.</li></ul>
<p><br />
</p>
<ul><li><code>checked</code> = boolean<br />If present, indicates that the command is selected.<br />The attribute must be omitted unless the type attribute is in either the Checkbox state or the Radio state.</li></ul>
<p><br />
</p>
<ul><li><code>radiogroup</code> = string<br />Gives the name of the group of commands that will be toggled when the command itself is toggled, for commands whose type attribute has the value "radio".</li></ul>
<p><br />
See also <a href="/w/index.php?title=HTML/Attributes/_Global&amp;action=edit&amp;redlink=1" class="new" title="HTML/Attributes/ Global (page does not exist)">global attributes</a>.
</p><p>Also, the title attribute has special semantics on this element.
</p><p><br />
</p>
<h2><span class="mw-headline" id="Examples">Examples</span></h2>
<h3><span class="mw-headline" id="Example_A">Example A</span></h3>
<p>[try it]:
</p>
<pre>
&lt;menu type=&quot;toolbar&quot;&gt;
  &lt;command type=&quot;radio&quot; radiogroup=&quot;alignment&quot; checked=&quot;checked&quot;
          label=&quot;Left&quot; icon=&quot;icons/alL.png&quot; onclick=&quot;setAlign('left')&quot;&gt;
  &lt;command type=&quot;radio&quot; radiogroup=&quot;alignment&quot;
          label=&quot;Center&quot; icon=&quot;icons/alC.png&quot; onclick=&quot;setAlign('center')&quot;&gt;
  &lt;command type=&quot;radio&quot; radiogroup=&quot;alignment&quot;
          label=&quot;Right&quot; icon=&quot;icons/alR.png&quot; onclick=&quot;setAlign('right')&quot;&gt;
  &lt;hr&gt;
  &lt;command type=&quot;command&quot; disabled=&quot;disabled&quot;
          label=&quot;Publish&quot; icon=&quot;icons/pub.png&quot; onclick=&quot;publish()&quot;&gt;
&lt;/menu&gt;
</pre>
<p><br />
</p>
<h2><span class="mw-headline" id="HTML_Reference">HTML Reference</span></h2>
<p>The HTML5 specification defines the &lt;command&gt; element in <a rel="nofollow" class="external text" href="http://www.w3.org/TR/html5/interactive-elements.html#the-command-element">4.12.3 The command element</a>.
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

<!-- Saved in parser cache with key wpwiki:pcache:idhash:925-0!*!0!!*!*!*!esi=1 and timestamp 20150731181623 and revision id 100890
 -->
