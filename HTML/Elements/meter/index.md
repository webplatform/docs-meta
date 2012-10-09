{{Page_Title}}
{{Flags
|High-level issues=Merge Candidate
}}
{{Standardization_Status}}
{{API_Name}}
{{Summary_Section}}
{{Markup_Element
|Content=<div style='float: right;background: white;border:1px dashed black;padding: 1ex;margin-left:1ex;'>

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

= &lt;meter&gt; =

The &lt;meter&gt; element represents a scalar measurement within a known range, or a fractional value.

== Point ==
*Example of meter:
**disk usage
**relevance of a query result
**fraction of a voting population to have selected a particular candidate ...


*The meter element should not be used to indicate progress (as in a progress bar). For that role, HTML provides a separate progress element.


*The meter element also does not represent a scalar value of arbitrary range — for example, it would be wrong to use this to report a weight, or height, unless there is a known maximum value. [[#Example_of_bad_usage|[Example of bad usage]]]


*Authors are encouraged to include a textual representation of the gauge's state in the element's contents, for users of user agents that do not support the meter element.

== HTML Attributes ==
*<code>value</code> = valid floating point numbers<br />Specifies the value to have the gauge indicate as the "measured" value.<br />The value attribute must be specified.


*<code>min</code> = valid floating point numbers<br />Specifies the lower bound of the range.


*<code>max</code> = valid floating point numbers<br />Specifies the upper bound


*<code>low</code> = valid floating point numbers<br />Specifies the range that is considered to be the "low" part.


*<code>high</code> = valid floating point numbers<br />Specifies the range that is considered to be the "high" part.


*<code>optimum</code> = valid floating point numbers<br />Gives the position that is "optimum":
**If that is higher than the "high" value then this indicates that the higher the value, the better
**if it's lower than the "low" mark then it indicates that lower values are better
**if it is in between then it indicates that neither high nor low values are good.


See also [[HTML/Attributes/_Global|global attributes]].


== Examples ==

=== Example A ===
The following examples show three gauges that would all be three-quarters full [try it]:
<pre>
Storage space usage: <meter value=6 max=8>6 blocks used (out of 8 total)</meter>
Voter turnout: <meter value=0.75><img alt="75%" src="graph75.png"></meter>
Tickets sold: <meter min="0" max="100" value="75"></meter>
</pre>

[[File:Meter01.png]]

=== Example B ===
There is no explicit way to specify units in the meter element, but the units may be specified in the title attribute in free-form text [try it]:
<pre>
<dl>
  <dt>Radius: <dd> <meter min=0 max=20 value=12 title="centimeters">12cm</meter>
  <dt>Height: <dd> <meter min=0 max=10 value=2 title="centimeters">2cm</meter>
</dl>
</pre>


=== <span style="color:#9c0037;">Example of bad usage</span> ===
The following example is incorrect use of the element, because it doesn't give a range (and since the default maximum is 1, both of the gauges would end up looking maxed out)
<pre style="color:gray;">
<!-- do not copy this example, it is an example of bad usage! -->
<p>The grapefruit pie had a radius of <meter value=12>12cm</meter>
and a height of <meter value=2>2cm</meter>.</p>
</pre> 


== HTML Reference ==

The HTML5 specification defines the &lt;meter&gt; element in [http://www.w3.org/TR/html5/the-button-element.html#the-meter-element 4.10.17 The meter element].

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
|Desktop_rows={{Compatibility Table Desktop Row
|Chrome_supported=Yes
|Chrome_prefixed_supported=Unknown
|Chrome_prefixed_version=
|Firefox_supported=Yes
|Firefox_version=16+
|Firefox_prefixed_supported=Unknown
|Firefox_prefixed_version=
|Internet_explorer_supported=No
|Internet_explorer_version=
|Internet_explorer_prefixed_supported=Unknown
|Internet_explorer_prefixed_version=
|Opera_supported=Yes
|Opera_prefixed_supported=Unknown
|Opera_prefixed_version=
|Safari_supported=Yes
|Safari_version=6+
|Safari_prefixed_supported=Unknown
|Safari_prefixed_version=
}}
|Mobile_rows={{Compatibility Table Mobile Row
|Android_supported=No
|Android_version=
|Android_prefixed_supported=Unknown
|Android_prefixed_version=
|Blackberry_supported=Yes
|Blackberry_version=7+
|Blackberry_prefixed_supported=Unknown
|Blackberry_prefixed_version=
|Chrome_mobile_supported=Unknown
|Chrome_mobile_version=
|Chrome_mobile_prefixed_supported=Unknown
|Chrome_mobile_prefixed_version=
|Firefox_mobile_supported=Unknown
|Firefox_mobile_version=
|Firefox_mobile_prefixed_supported=Unknown
|Firefox_mobile_prefixed_version=
|IE_mobile_supported=Unknown
|IE_mobile_version=
|IE_mobile_prefixed_supported=Unknown
|IE_mobile_prefixed_version=
|Opera_mobile_supported=No
|Opera_mobile_version=
|Opera_mobile_prefixed_supported=Unknown
|Opera_mobile_prefixed_version=
|Opera_mini_supported=No
|Opera_mini_version=
|Opera_mini_prefixed_supported=Unknown
|Opera_mini_prefixed_version=
|Safari_mobile_supported=No
|Safari_mobile_version=
|Safari_mobile_prefixed_supported=Unknown
|Safari_mobile_prefixed_version=
}}
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