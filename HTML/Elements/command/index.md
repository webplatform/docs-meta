{{Page_Title}}
{{Flags
|State=Unreviewed
|Editorial notes=Can't find a normative reference. Is this obsolete?
|Checked_Out=No
|High-level issues=Merge Candidate
}}
{{Standardization_Status|Experimental}}
{{API_Name}}
{{Summary_Section}}
{{Markup_Element
|DOM_interface=
|Tag_omissions=
|CSS_display=
|Content=

= &lt;command&gt; =

The &lt;command&gt; element represents a command that the user can invoke.

== Point ==

*A command can be part of a context menu or toolbar, using the menu element, or can be put anywhere else in the page, to define a keyboard shortcut.


== HTML Attributes ==
*<code>type</code> = command/ checkbox/ radio<br />Indicates the kind of command:
**command<br />Normal command with an associated action.
**checkbox<br />State or option that can be toggled.
**radio<br />Selection of one item from a list of items.


*<code>label</code> = string<br />Gives the name of the command, as shown to the user.<br />The label attribute must be specified and must have a value that is not the empty string.


*<code>icon</code> = valid non-empty URL potentially<br />Gives a picture that represents the command.


*<code>disabled</code> = boolean<br />If present, indicates that the command is not available in the current state.


*<code>checked</code> = boolean<br />If present, indicates that the command is selected.<br />The attribute must be omitted unless the type attribute is in either the Checkbox state or the Radio state.


*<code>radiogroup</code> = string<br />Gives the name of the group of commands that will be toggled when the command itself is toggled, for commands whose type attribute has the value "radio".


See also [[HTML/Attributes/_Global|global attributes]].

Also, the title attribute has special semantics on this element.


== Examples ==

=== Example A ===
[try it]:
<pre>
<menu type="toolbar">
  <command type="radio" radiogroup="alignment" checked="checked"
          label="Left" icon="icons/alL.png" onclick="setAlign('left')">
  <command type="radio" radiogroup="alignment"
          label="Center" icon="icons/alC.png" onclick="setAlign('center')">
  <command type="radio" radiogroup="alignment"
          label="Right" icon="icons/alR.png" onclick="setAlign('right')">
  <hr>
  <command type="command" disabled="disabled"
          label="Publish" icon="icons/pub.png" onclick="publish()">
</menu>
</pre>


== HTML Reference ==

The HTML5 specification defines the &lt;command&gt; element in [http://www.w3.org/TR/html5/interactive-elements.html#the-command-element 4.12.3 The command element].

[[Category:HTML]]
[[Category:HTMLElement]]
}}
{{Examples_Section
|Not_required=No
|Examples=
}}
{{Notes_Section
|Usage=
|Notes=
|Import_Notes=
}}
{{Related_Specifications_Section
|Specifications=
}}
{{See_Also_Section
|Manual_links=
|External_links=
|Manual_sections=
}}
{{Topics|HTML}}
{{External_Attribution
|Is_CC-BY-SA=No
|MDN_link=
|MSDN_link=
|HTML5Rocks_link=
}}
{{Compatibility_Section
|Not_required=No
|Desktop_rows=
|Mobile_rows=
|Notes_rows=
}}