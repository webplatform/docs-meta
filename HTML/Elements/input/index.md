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

= &lt;input&gt; =

The &lt;input&gt; element represents a typed data field, usually with a form control to allow the user to edit the data.

== Point ==
*The type attribute controls the data type (and associated control) of the element. It is an enumerated attribute.


*The following table lists the keywords and states for the attribute.<br />The keywords in the left column map to the states in the cell in the second column on the same row as the keyword.



<table class="filehistory"><tr><th> Keyword
     </th><th> State
     </th><th> Data type
     </th><th> Control type
   </th></tr><tr><td><code>[[HTML/Elements/input/hidden|hidden]]</code>

     </td><td>Hidden
     </td><td> An arbitrary string
     </td><td> n/a
    </td></tr><tr><td><code>[[HTML/Elements/input/text|text]]</code>
     </td><td>Text
     </td><td> Text with no line breaks
     </td><td> Text field
    </td></tr><tr><td><code>[[HTML/Elements/input/search|search]]</code>

     </td><td>Search
     </td><td> Text with no line breaks
     </td><td> Search field
    </td></tr><tr><td><code>[[HTML/Elements/input/tel|tel]]</code>
     </td><td>Telephone
     </td><td> Text with no line breaks
     </td><td> A text field
    </td></tr><tr><td><code>[[HTML/Elements/input/url|url]]</code>

     </td><td> URL
     </td><td> An absolute IRI
     </td><td> A text field
    </td></tr><tr><td><code>[[HTML/Elements/input/email|email]]</code>
     </td><td>E-mail
     </td><td> An e-mail address or list of e-mail addresses
     </td><td> A text field
    </td></tr><tr><td><code>[[HTML/Elements/input/password|password]]</code>

     </td><td>Password
     </td><td> Text with no line breaks (sensitive information)
     </td><td> Text field that obscures data entry
    </td></tr><tr><td><code>[[HTML/Elements/input/datetime|datetime]]</code>
     </td><td>Date and Time
     </td><td> A date and time (year, month, day, hour, minute, second, fraction of a second) with the time zone set to UTC
     </td><td> A date and time control
    </td></tr><tr><td><code>[[HTML/Elements/input/date|date]]</code>

     </td><td>Date
     </td><td> A date (year, month, day) with no time zone
     </td><td> A date control
    </td></tr><tr><td><code>[[HTML/Elements/input/month|month]]</code>
     </td><td>Month
     </td><td> A date consisting of a year and a month with no time zone
     </td><td> A month control
    </td></tr><tr><td><code>[[HTML/Elements/input/week|week]]</code>

     </td><td>Week
     </td><td> A date consisting of a week-year number and a week number with no time zone
     </td><td> A week control
    </td></tr><tr><td><code>[[HTML/Elements/input/time|time]]</code>
     </td><td>Time
     </td><td> A time (hour, minute, seconds, fractional seconds) with no time zone
     </td><td> A time control
    </td></tr><tr><td><code>[[HTML/Elements/input/datetime-local|datetime-local]]</code>

     </td><td>Local Date and Time
     </td><td> A date and time (year, month, day, hour, minute, second, fraction of a second) with no time zone
     </td><td> A date and time control
    </td></tr><tr><td><code>[[HTML/Elements/input/number|number]]</code>
     </td><td>Number
     </td><td> A numerical value
     </td><td> A text field or spinner control
    </td></tr><tr><td><code>[[HTML/Elements/input/range|range]]</code>

     </td><td>Range
     </td><td> A numerical value, with the extra semantic that the exact value is not important
     </td><td> A slider control or similar
    </td></tr><tr><td><code>[[HTML/Elements/input/color|color]]</code>
     </td><td>Color
     </td><td> An sRGB color with 8-bit red, green, and blue components
     </td><td> A color well
    </td></tr><tr><td><code>[[HTML/Elements/input/checkbox|checkbox]]</code>

     </td><td>Checkbox
     </td><td> A set of zero or more values from a predefined list
     </td><td> A checkbox
    </td></tr><tr><td><code>[[HTML/Elements/input/radio|radio]]</code>
     </td><td>Radio Button
     </td><td> An enumerated value
     </td><td> A radio button
    </td></tr><tr><td><code>[[HTML/Elements/input/file|file]]</code>

     </td><td>File Upload
     </td><td> Zero or more files each with a MIME type and optionally a file name
     </td><td> A label and a button
    </td></tr><tr><td><code>[[HTML/Elements/input/submit|submit]]</code>
     </td><td>Submit Button
     </td><td> An enumerated value, with the extra semantic that it must be the last value selected and initiates form submission
     </td><td> A button
    </td></tr><tr><td><code>[[HTML/Elements/input/image|image]]</code>
     </td><td>Image Button
     </td><td> A coordinate, relative to a particular image's size, with the extra semantic that it must be the last value selected and initiates form submission
     </td><td> Either a clickable image, or a button
    </td></tr><tr><td><code>[[HTML/Elements/input/reset|reset]]</code>
     </td><td>Reset Button
     </td><td> n/a
     </td><td> A button
    </td></tr><tr><td><code>[[HTML/Elements/input/button|button]]</code>
     </td><td>Button
     </td><td> n/a
     </td><td> A button
  </td></tr></table>



== HTML Attributes ==
*Which of the attributes apply to an input element depends on the state of its type attribute. The following table is summarizes which of those content attributes.


<table  class="filehistory"><tr><th>
     </th><th>Hidden
     </th><th>Text, Search, URL, Telephone
     </th><th>E-mail
     </th><th>Password
     </th><th>Date and Time, Date, Month, Week, Time
     </th><th>Local Date and Time, Number
     </th><th>Range
     </th><th>Color
     </th><th>Checkbox, Radio Button
     </th><th>File Upload
     </th><th>Submit Button
     </th><th>Image Button
     </th><th>Reset Button, Button
   </th></tr><tr><th colspan="14" scope="rowgroup">Content attributes
    </th></tr><tr><th> <code title="attr-input-accept">accept</code>
     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->

     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->

     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="yes"> Yes     <!-- File Upload -->

     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-alt">alt</code>
     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->

     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->

     </td><td class="yes"> Yes     <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-autocomplete">autocomplete</code>
     </th><td class="no"> &#183; <!-- Hidden -->

     </td><td class="yes"> Yes     <!-- Text -->
<!-- <td class="yes"> Yes          Search -->
<!-- <td class="yes"> Yes          URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->
     </td><td class="yes"> Yes     <!-- Password -->
     </td><td class="yes"> Yes     <!-- Date and Time -->

<!-- <td class="yes"> Yes          Date -->
<!-- <td class="yes"> Yes          Month -->
<!-- <td class="yes"> Yes          Week -->
<!-- <td class="yes"> Yes          Time -->
     </td><td class="yes"> Yes     <!-- Local Date and Time -->
<!-- <td class="yes"> Yes          Number -->
     </td><td class="yes"> Yes     <!-- Range -->
     </td><td class="yes"> Yes     <!-- Color -->

     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->

     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-checked">checked</code></th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->

<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="yes"> Yes     <!-- Checkbox -->

<!-- <td class="yes"> Yes          Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->

<!-- <td class="no"> &middot;      Button -->
    </td></tr><tr><th> <code title="attr-fs-formaction">formaction</code>
     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->

     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->

     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->

     </td><td class="yes"> Yes     <!-- Submit Button -->
     </td><td class="yes"> Yes     <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-fs-formenctype">formenctype</code>
     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->

     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->

     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="yes"> Yes     <!-- Submit Button -->

     </td><td class="yes"> Yes     <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-fs-formmethod">formmethod</code>
     </th><td class="no"> &#183; <!-- Hidden -->

     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->

<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->

     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="yes"> Yes     <!-- Submit Button -->
     </td><td class="yes"> Yes     <!-- Image Button -->

     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->
    </td></tr><tr><th> <code title="attr-fs-formnovalidate">formnovalidate</code></th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->

<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->

<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->

<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="yes"> Yes     <!-- Submit Button -->
     </td><td class="yes"> Yes     <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->

<!-- <td class="no"> &middot;      Button -->
    </td></tr><tr><th> <code title="attr-fs-formtarget">formtarget</code>
     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->

     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->

     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->

     </td><td class="yes"> Yes     <!-- Submit Button -->
     </td><td class="yes"> Yes     <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-dim-height">height</code>

     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->

     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->

     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->

     </td><td class="yes"> Yes     <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-list">list</code>
     </th><td class="no"> &#183; <!-- Hidden -->

     </td><td class="yes"> Yes     <!-- Text -->
<!-- <td class="yes"> Yes          Search -->
<!-- <td class="yes"> Yes          URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="yes"> Yes     <!-- Date and Time -->

<!-- <td class="yes"> Yes          Date -->
<!-- <td class="yes"> Yes          Month -->
<!-- <td class="yes"> Yes          Week -->
<!-- <td class="yes"> Yes          Time -->
     </td><td class="yes"> Yes     <!-- Local Date and Time -->
<!-- <td class="yes"> Yes          Number -->
     </td><td class="yes"> Yes     <!-- Range -->
     </td><td class="yes"> Yes     <!-- Color -->

     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->

     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-max">max</code></th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->

<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="yes"> Yes     <!-- Date and Time -->
<!-- <td class="yes"> Yes          Date -->
<!-- <td class="yes"> Yes          Month -->
<!-- <td class="yes"> Yes          Week -->

<!-- <td class="yes"> Yes          Time -->
     </td><td class="yes"> Yes     <!-- Local Date and Time -->
<!-- <td class="yes"> Yes          Number -->
     </td><td class="yes"> Yes     <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->

<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->

<!-- <td class="no"> &middot;      Button -->
    </td></tr><tr><th> <code title="attr-input-maxlength">maxlength</code>
     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="yes"> Yes     <!-- Text -->
<!-- <td class="yes"> Yes          Search -->
<!-- <td class="yes"> Yes          URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->

     </td><td class="yes"> Yes     <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->

     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->

     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-min">min</code>

     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->

     </td><td class="yes"> Yes     <!-- Date and Time -->
<!-- <td class="yes"> Yes          Date -->
<!-- <td class="yes"> Yes          Month -->
<!-- <td class="yes"> Yes          Week -->
<!-- <td class="yes"> Yes          Time -->
     </td><td class="yes"> Yes     <!-- Local Date and Time -->
<!-- <td class="yes"> Yes          Number -->
     </td><td class="yes"> Yes     <!-- Range -->

     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->

     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-multiple">multiple</code>
     </th><td class="no"> &#183; <!-- Hidden -->

     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->

<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->

     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="yes"> Yes     <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->

     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-pattern">pattern</code></th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="yes"> Yes     <!-- Text -->

<!-- <td class="yes"> Yes          Search -->
<!-- <td class="yes"> Yes          URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->
     </td><td class="yes"> Yes     <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->

<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->

<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->

<!-- <td class="no"> &middot;      Button -->
    </td></tr><tr><th> <code title="attr-input-placeholder">placeholder</code>
     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="yes"> Yes     <!-- Text -->
<!-- <td class="yes"> Yes          Search -->
<!-- <td class="yes"> Yes          URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->

     </td><td class="yes"> Yes     <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> Yes      Number -->

     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->

     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-readonly">readonly</code>

     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="yes"> Yes     <!-- Text -->
<!-- <td class="yes"> Yes          Search -->
<!-- <td class="yes"> Yes          URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->
     </td><td class="yes"> Yes     <!-- Password -->

     </td><td class="yes"> Yes     <!-- Date and Time -->
<!-- <td class="yes"> Yes          Date -->
<!-- <td class="yes"> Yes          Month -->
<!-- <td class="yes"> Yes          Week -->
<!-- <td class="yes"> Yes          Time -->
     </td><td class="yes"> Yes     <!-- Local Date and Time -->
<!-- <td class="yes"> Yes          Number -->
     </td><td class="no"> &#183; <!-- Range -->

     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->

     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-required">required</code>
     </th><td class="no"> &#183; <!-- Hidden -->

     </td><td class="yes"> Yes     <!-- Text -->
<!-- <td class="yes"> Yes          Search -->
<!-- <td class="yes"> Yes          URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->
     </td><td class="yes"> Yes     <!-- Password -->
     </td><td class="yes"> Yes     <!-- Date and Time -->

<!-- <td class="yes"> Yes          Date -->
<!-- <td class="yes"> Yes          Month -->
<!-- <td class="yes"> Yes          Week -->
<!-- <td class="yes"> Yes          Time -->
     </td><td class="yes"> Yes     <!-- Local Date and Time -->
<!-- <td class="yes"> Yes          Number -->
     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->

     </td><td class="yes"> Yes     <!-- Checkbox -->
<!-- <td class="yes"> Yes          Radio Button -->
     </td><td class="yes"> Yes     <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->

     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-size">size</code></th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="yes"> Yes     <!-- Text -->

<!-- <td class="yes"> Yes          Search -->
<!-- <td class="yes"> Yes          URL -->
     </td><td class="yes"> Yes     <!-- E-mail -->
     </td><td class="yes"> Yes     <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->

<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->

<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->

<!-- <td class="no"> &middot;      Button -->
    </td></tr><tr><th> <code title="attr-input-src">src</code>
     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->

     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->
<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->

     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->

     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="yes"> Yes     <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-input-step">step</code>

     </th><td class="no"> &#183; <!-- Hidden -->
     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->

     </td><td class="yes"> Yes     <!-- Date and Time -->
<!-- <td class="yes"> Yes          Date -->
<!-- <td class="yes"> Yes          Month -->
<!-- <td class="yes"> Yes          Week -->
<!-- <td class="yes"> Yes          Time -->
     </td><td class="yes"> Yes     <!-- Local Date and Time -->
<!-- <td class="yes"> Yes          Number -->
     </td><td class="yes"> Yes     <!-- Range -->

     </td><td class="no"> &#183; <!-- Color -->
     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->

     </td><td class="no"> &#183; <!-- Image Button -->
     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

    </td></tr><tr><th> <code title="attr-dim-width">width</code>
     </th><td class="no"> &#183; <!-- Hidden -->

     </td><td class="no"> &#183; <!-- Text -->
<!-- <td class="no"> &middot;      Search -->
<!-- <td class="no"> &middot;      URL -->
     </td><td class="no"> &#183; <!-- E-mail -->
     </td><td class="no"> &#183; <!-- Password -->
     </td><td class="no"> &#183; <!-- Date and Time -->

<!-- <td class="no"> &middot;      Date -->
<!-- <td class="no"> &middot;      Month -->
<!-- <td class="no"> &middot;      Week -->
<!-- <td class="no"> &middot;      Time -->
     </td><td class="no"> &#183; <!-- Local Date and Time -->
<!-- <td class="no"> &middot;      Number -->
     </td><td class="no"> &#183; <!-- Range -->
     </td><td class="no"> &#183; <!-- Color -->

     </td><td class="no"> &#183; <!-- Checkbox -->
<!-- <td class="no"> &middot;      Radio Button -->
     </td><td class="no"> &#183; <!-- File Upload -->
     </td><td class="no"> &#183; <!-- Submit Button -->
     </td><td class="yes"> Yes     <!-- Image Button -->

     </td><td class="no"> &#183; <!-- Reset Button -->
<!-- <td class="no"> &middot;      Button -->

   </td></tr></table>



See also [[HTML/Attributes/_Global|global attributes]].



== HTML Reference ==

The HTML5 specification defines the &lt;input&gt; element in [http://www.w3.org/TR/html5/the-input-element.html#the-input-element 4.10.7 The input element].

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