{{Page_Title}}
{{Flags
|High-level issues=Merge Candidate
}}
{{Standardization_Status}}
{{API_Name}}
{{Summary_Section}}
{{Markup_Element
|Content=

<div style='float: right;background: white;border:1px dashed black;padding: 1ex;margin-left:1ex;'>

* [[HTML/Elements|List of Elements]]
** [[HTML/Elements#Forms|Forms]]
*** [[HTML/Elements/form|form]]
*** [[HTML/Elements/fieldset|fieldset]]
*** [[HTML/Elements/legend|legend]]
*** [[HTML/Elements/label|label]]
*** [[HTML/Elements/input|input]]
*** [[HTML/Elements/button|button]]
*** [[HTML/Elements/select|select]]
*** [[HTML/Elements/datalist|datalist]]
*** [[HTML/Elements/optgroup|optgroup]]
*** [[HTML/Elements/option|option]]
*** [[HTML/Elements/textarea|textarea]]
*** [[HTML/Elements/keygen|keygen]]
*** [[HTML/Elements/output|output]]
*** [[HTML/Elements/progress|progress]]
*** [[HTML/Elements/meter|meter]]

</div>

= &lt;optgroup&gt; =

The &lt;optgroup&gt; element represents a group of option elements with a common label.

== Point ==
*The label attribute must be specified. [[#Example_A|[Example A]]]


== HTML Attributes ==
*<code>disabled</code> = boolean<br />if present, disable a group of option elements together.


*<code>label</code> = string<br />Its value gives the name of the group, for the purposes of the user interface.


See [[HTML/Attributes/_Global|global attributes]].


== Examples ==

=== Example A ===
[try it]:
<pre>
<form action="courseselector.dll" method="get">
  <p>Which course would you like to watch today?
  <p><label>Course:
    <select name="c">
      <optgroup label="8.01 Physics I: Classical Mechanics">
        <option value="8.01.1">Lecture 01: Powers of Ten</option>
        <option value="8.01.2">Lecture 02: 1D Kinematics</option>
        <option value="8.01.3">Lecture 03: Vectors</option>
      </optgroup>
      <optgroup label="8.02 Electricity and Magnestism">
        <option value="8.02.1">Lecture 01: What holds our world together?</option>
        <option value="8.02.2">Lecture 02: Electric Field</option>
        <option value="8.02.3">Lecture 03: Electric Flux</option>
      </optgroup>
      <optgroup label="8.03 Physics III: Vibrations and Waves">
        <option value="8.03.1">Lecture 01: Periodic Phenomenon</option>
        <option value="8.03.2">Lecture 02: Beats</option>
        <option value="8.03.3">Lecture 03: Forced Oscillations with Damping</option>
      </optgroup>
    </select>
  </label>
  <p><input type=submit value="▶ Play">
</form>
</pre>

== HTML Reference ==

The HTML5 specification defines the &lt;optgroup&gt; element in [http://www.w3.org/TR/html5/the-button-element.html#the-optgroup-element 4.10.11 The optgroup element].

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