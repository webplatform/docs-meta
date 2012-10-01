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
** [[HTML/Elements#Tables|Tables]]
*** [[HTML/Elements/table|table]]
*** [[HTML/Elements/caption|caption]]
*** [[HTML/Elements/colgroup|colgroup]]
*** [[HTML/Elements/col|col]]
*** [[HTML/Elements/tbody|tbody]]
*** [[HTML/Elements/thead|thead]]
*** [[HTML/Elements/tfoot|tfoot]]
*** [[HTML/Elements/tr|tr]]
*** [[HTML/Elements/td|td]]
*** [[HTML/Elements/th|th]]

</div>

= &lt;table&gt; =

The &lt;table&gt; element represents data with more than one dimension, in the form of a table.

== Point ==

*Tables must not be used as layout aids. There are a variety of alternatives to using HTML tables for layout, primarily using CSS positioning and the CSS table model.
*Users might have difficulty understanding the content, authors should include explanatory information introducing the table. This information is useful for all users, but is especially useful for users who cannot see the table, e.g. users of screen readers.[[#Example_B|[Example B]]]
*Tables have rows and columns given by their descendants. A table must not have an empty row or column. 

== HTML Attributes ==
*<code>summary</code> = explanatory information introducing the table

See also [[HTML/Attributes/_Global|global attributes]].

== Examples ==

=== Example A ===
[try it]:
<pre>
<table>
  <caption>Characteristics with positive and negative sides</caption>
  <thead>
    <tr>
      <th>Characteristic</th>
      <th>Negative</th>
      <th>Positive</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Mood</th>
      <td>Sad</td>
      <td>Happy</td>
    </tr>
    <tr>
      <th>Grade</th>
      <td>Failing</td>
      <td>Passing</td>
    </tr>
  </tbody>
</table>
</pre>

[[File:Table01.png]]

=== Example B ===
The following example is including explanatory information introducing the table by next to the table in the same figure [try it]:
<pre>
<figure>
  <figcaption>Characteristics with positive and negative sides</figcaption>
  <p>Characteristics are given in the second column, with the
  negative side in the left column and the positive side in the right column.</p>
  <table>
    <thead>
      <tr>
        <th id="n">Negative</th>
        <th>Characteristic</th>
        <th id="p">Positive</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td headers="n r1">Sad</td>
        <th id="r1">Mood</th>
        <td headers="p r1">Happy</td>
      </tr>
      <tr>
        <td headers="n r2">Failing</td>
        <th id="r2">Grade</th>
        <td headers="p r2">Passing</td>
      </tr>
    </tbody>
   </table>
</figure>
</pre>

[[File:Table02.png]]

== HTML Reference ==

The HTML5 specification defines the &lt;table&gt; element in [http://www.w3.org/TR/html5/tabular-data.html#the-table-element 4.9.1 The table element].

== See also ==

* [[HTML_tables|HTML tables]]

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