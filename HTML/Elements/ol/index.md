{{Page_Title}}
{{Flags
|High-level issues=Merge Candidate
|Checked_Out=No
}}
{{Standardization_Status}}
{{API_Name}}
{{Summary_Section|The ol element makes an ''ordered list'' from the li (''list item'') elements it contains. Typically, each item is rendered with a number before it.}}
{{Markup_Element
|Content=<div style='float: right;background: white;border:1px dashed black;padding: 1ex;margin-left: 1ex;'>

* [[Meta:HTML/Elements|List of Elements]]
** [[Meta:HTML/Elements#Grouping_content|Grouping content]]
*** [[Meta:HTML/Elements/p|p]]
*** [[Meta:HTML/Elements/hr|hr]]
*** [[Meta:HTML/Elements/pre|pre]]
*** [[Meta:HTML/Elements/blockquote|blockquote]]
*** [[Meta:HTML/Elements/ol|ol]]
*** [[Meta:HTML/Elements/ul|ul]]
*** [[Meta:HTML/Elements/li|li]]
*** [[Meta:HTML/Elements/dl|dl]]
*** [[Meta:HTML/Elements/dt|dt]]
*** [[Meta:HTML/Elements/dd|dd]]
*** [[Meta:HTML/Elements/figure|figure]]
*** [[Meta:HTML/Elements/figcaption|figcaption]]
*** [[Meta:HTML/Elements/div|div]]
*** [[Meta:HTML/Elements/center|center]]

</div>

= &lt;ol&gt; =

The &lt;ol&gt; element represents an ''ordered list''. By default, most browsers add an integer as a marker before each list item:

# First list item
# Second list item
# Third list item

[[#Example_A|[Example A]]]

Use an ordered list where there's meaning to the order in which the list items appear. If the order is not important, it is more appropriate to use a [[Meta:HTML/Elements/ul|&lt;ul&gt;]] unordered list element.

== HTML Attributes ==

* <code>reversed</code><br />Renders numbers for the items in descending order list (...3, 2, 1), instead of the default ascending order (1, 2, 3...). [[#Example_B|[Example B]]]


* <code>start</code> = valid integer<br />Specifies the value for the first list item. [[#Example_C|[Example C]]]


* <code>type</code> = the kind of marker<br />Specifies the kind of marker to use in the list. [[#Example_D|[Example D]]]

<table class="wikitable">
    <tr>
      <th>
        Value
      </th>
      <th>
        Marker type
      </th>
    </tr>
    <tr>
      <td>
        1
      </td>
      <td>
        ''Default value'' Arabic numerals (1, 2, 3, 4)
      </td>
    </tr>
    <tr>
      <td>
        a
      </td>
      <td>
        Lowercase roman letters in alphabetical ordered (a, b, c, d)
      </td>
    </tr>
    <tr>
      <td>
        A
      </td>
      <td>
        Uppercase roman letters in alphabetical order (A, B, C, D)
      </td>
    </tr>
    <tr>
      <td>
        i
      </td>
      <td>
        Lowercase roman numerals numbers, lowercase (i, ii, iii, iv)
      </td>
    </tr>
    <tr>
      <td>
        I
      </td>
      <td>
        Uppercase roman numerals numbers, lowercase (I, II, III, IV)
      </td>
    </tr>
</table>


See also [[HTML/Attributes/_Global|global attributes]].

== Examples ==

=== Example A ===
[try it]
<pre>
<ol>
  <li>sample1</li>
  <li>sample2</li>
  <li>sample3</li>
</ol>
</pre>

[[File:Ol01.png]]

=== Example B ===
With the reversed attribute [try it]:
<pre>
<ol reversed>
  <li>sample1</li>
  <li>sample2</li>
  <li>sample3</li>
</ol> 
</pre>

[[File:Li02.png]]

=== Example C ===
With the start attribute [try it]:
<pre>
<ol start="101">
  <li>sample1</li>
  <li>sample2</li>
  <li>sample3</li>
</ol> 
</pre>

[[File:Ol03.png]]

=== Example D ===
With the type attribute [try it]:
<pre>
<ol type="lower-alpha">
  <li>sample1</li>
  <li>sample2</li>
  <li>sample3</li>
</ol> 
</pre>

[[File:Ol04.png]]

== HTML Reference ==

The HTML5 specification defines the &lt;ol&gt; element in [http://www.w3.org/TR/html5/grouping-content.html#the-ol-element 4.5.5 The ol element].

== See also ==

* [[guides/html lists|HTML Lists]]

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
|Imported_tables=
|Desktop_rows=
|Mobile_rows=
|Notes_rows=
}}
{{See_Also_Section
|Topic_clusters=HTML
}}
{{Topics|HTML}}
{{External_Attribution
|Is_CC-BY-SA=No
|MDN_link=
|MSDN_link=
|HTML5Rocks_link=
}}