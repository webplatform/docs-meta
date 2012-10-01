{{Page_Title}}
{{Flags
|High-level issues=Merge Candidate
}}
{{Standardization_Status}}
{{API_Name}}
{{Summary_Section}}
{{Markup_Element
|Content=

<div style='float: right;background: white;border:1px dashed black;padding: 1ex;margin-left: 1ex;'>

* [[HTML/Elements|List of Elements]]
** [[HTML/Elements#Interactive|Interactive]]
*** [[HTML/Elements/details|details]]
*** [[HTML/Elements/summary|summary]]
*** [[HTML/Elements/command|command]]
*** [[HTML/Elements/menu|menu]]

</div>

= &lt;menu&gt; =

The &lt;menu&gt; element represents a list of commands.

== HTML Attributes ==
*<code>type</code> = context/ toolbar/ list<br />Indicates the kind of menu being declared:
**context<br />the commands of a context menu, and the user can only interact with the commands if that context menu is activated. [[#Example_B|[Example B]]]
**toolbar<br />A list of active commands that the user can immediately interact with. [[#Example_A|[Example A]]]
**list<br />an unordered list of items (each represented by an li element), each of which represents a command that the user can perform or activate, or, if the element has no li element children, flow content describing available commands.


*<code>label</code> = string<br />Gives the label of the menu.


See also [[HTML/Attributes/_Global|global attributes]].


== Examples ==

=== Example A ===
For example, the following represents a toolbar with three menu buttons on it, each of which has a dropdown menu with a series of options [try it]:
<pre>
<menu type="toolbar">
  <li>
    <menu label="File">
      <button type="button" onclick="fnew()">New...</button>
      <button type="button" onclick="fopen()">Open...</button>
      <button type="button" onclick="fsave()">Save</button>
      <button type="button" onclick="fsaveas()">Save as...</button>
    </menu>
  </li>
  <li>
    <menu label="Edit">
      <button type="button" onclick="ecopy()">Copy</button>
      <button type="button" onclick="ecut()">Cut</button>
      <button type="button" onclick="epaste()">Paste</button>
    </menu>
  </li>
  <li>
    <menu label="Help">
      <li><a href="help.html">Help</a></li>
      <li><a href="about.html">About</a></li>
    </menu>
  </li>
</menu>
</pre>

[[File:Menu01.png]]


=== Example B ===
Here is an example of a context menu for an input control [try it]:
<pre>
<form name="npc">
  <label>Character name: <input name=char type=text contextmenu=namemenu required></label>
   <menu type=context id=namemenu>
     <command label="Pick random name"
        onclick="document.forms.npc.elements.char.value = getRandomName()">
     <command label="Prefill other fields based on name"
        onclick="prefillFields(document.forms.npc.elements.char.value)">
   </menu>
</form>
</pre>


== HTML Reference ==

The HTML5 specification defines the &lt;menu&gt; element in [http://www.w3.org/TR/html5/interactive-elements.html#the-menu-element 4.12.4 The menu element].

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