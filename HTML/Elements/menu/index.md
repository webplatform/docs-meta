---
title: Meta:HTML/Elements/menu
---
<h1><span class="mw-headline" id="menu">menu</span></h1>
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
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">Interactive</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements/details&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/details (page does not exist)">details</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/summary&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/summary (page does not exist)">summary</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/command&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/command (page does not exist)">command</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/menu&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/menu (page does not exist)">menu</a></li></ul></li></ul></li></ul>
</div>
<h1><span class="mw-headline" id=".3Cmenu.3E">&lt;menu&gt;</span></h1>
<p>The &lt;menu&gt; element represents a list of commands.
</p>
<h2><span class="mw-headline" id="HTML_Attributes">HTML Attributes</span></h2>
<ul><li><code>type</code> = context/ toolbar/ list<br />Indicates the kind of menu being declared:
<ul><li>context<br />the commands of a context menu, and the user can only interact with the commands if that context menu is activated. <a href="#Example_B">[Example B]</a></li>
<li>toolbar<br />A list of active commands that the user can immediately interact with. <a href="#Example_A">[Example A]</a></li>
<li>list<br />an unordered list of items (each represented by an li element), each of which represents a command that the user can perform or activate, or, if the element has no li element children, flow content describing available commands.</li></ul></li></ul>
<p><br />
</p>
<ul><li><code>label</code> = string<br />Gives the label of the menu.</li></ul>
<p><br />
See also <a href="/w/index.php?title=HTML/Attributes/_Global&amp;action=edit&amp;redlink=1" class="new" title="HTML/Attributes/ Global (page does not exist)">global attributes</a>.
</p><p><br />
</p>
<h2><span class="mw-headline" id="Examples">Examples</span></h2>
<h3><span class="mw-headline" id="Example_A">Example A</span></h3>
<p>For example, the following represents a toolbar with three menu buttons on it, each of which has a dropdown menu with a series of options [try it]:
</p>
<pre>
&lt;menu type=&quot;toolbar&quot;&gt;
  &lt;li&gt;
    &lt;menu label=&quot;File&quot;&gt;
      &lt;button type=&quot;button&quot; onclick=&quot;fnew()&quot;&gt;New...&lt;/button&gt;
      &lt;button type=&quot;button&quot; onclick=&quot;fopen()&quot;&gt;Open...&lt;/button&gt;
      &lt;button type=&quot;button&quot; onclick=&quot;fsave()&quot;&gt;Save&lt;/button&gt;
      &lt;button type=&quot;button&quot; onclick=&quot;fsaveas()&quot;&gt;Save as...&lt;/button&gt;
    &lt;/menu&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;menu label=&quot;Edit&quot;&gt;
      &lt;button type=&quot;button&quot; onclick=&quot;ecopy()&quot;&gt;Copy&lt;/button&gt;
      &lt;button type=&quot;button&quot; onclick=&quot;ecut()&quot;&gt;Cut&lt;/button&gt;
      &lt;button type=&quot;button&quot; onclick=&quot;epaste()&quot;&gt;Paste&lt;/button&gt;
    &lt;/menu&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;menu label=&quot;Help&quot;&gt;
      &lt;li&gt;&lt;a href=&quot;help.html&quot;&gt;Help&lt;/a&gt;&lt;/li&gt;
      &lt;li&gt;&lt;a href=&quot;about.html&quot;&gt;About&lt;/a&gt;&lt;/li&gt;
    &lt;/menu&gt;
  &lt;/li&gt;
&lt;/menu&gt;
</pre>
<p><a href="/w/index.php?title=Special:Upload&amp;wpDestFile=Menu01.png" class="new" title="File:Menu01.png">File:Menu01.png</a>
</p><p><br />
</p>
<h3><span class="mw-headline" id="Example_B">Example B</span></h3>
<p>Here is an example of a context menu for an input control [try it]:
</p>
<pre>
&lt;form name=&quot;npc&quot;&gt;
  &lt;label&gt;Character name: &lt;input name=char type=text contextmenu=namemenu required&gt;&lt;/label&gt;
   &lt;menu type=context id=namemenu&gt;
     &lt;command label=&quot;Pick random name&quot;
        onclick=&quot;document.forms.npc.elements.char.value = getRandomName()&quot;&gt;
     &lt;command label=&quot;Prefill other fields based on name&quot;
        onclick=&quot;prefillFields(document.forms.npc.elements.char.value)&quot;&gt;
   &lt;/menu&gt;
&lt;/form&gt;
</pre>
<p><br />
</p>
<h2><span class="mw-headline" id="HTML_Reference">HTML Reference</span></h2>
<p>The HTML5 specification defines the &lt;menu&gt; element in <a rel="nofollow" class="external text" href="http://www.w3.org/TR/html5/interactive-elements.html#the-menu-element">4.12.4 The menu element</a>.
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

<!-- Saved in parser cache with key wpwiki:pcache:idhash:926-0!*!0!!*!5!*!esi=1 and timestamp 20150731181629 and revision id 5698
 -->
