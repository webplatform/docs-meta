---
title: input
overview_table:
  '[DOM Interface](/dom/interface)': '[?](/w/index.php?title=%3F&action=edit&redlink=1)'
tags:
  - HTML
  - HTMLElement
  - Markup
  - Elements
todo_broken_links:
  note: 'During import MediaWiki could not find the following links, please fix and adjust this list.'
  links:
    - '?'
    - HTML/Elements
    - HTML/Elements/form
    - HTML/Elements/fieldset
    - HTML/Elements/legend
    - HTML/Elements/label
    - HTML/Elements/input
    - HTML/Elements/button
    - HTML/Elements/select
    - HTML/Elements/datalist
    - HTML/Elements/optgroup
    - HTML/Elements/option
    - HTML/Elements/textarea
    - HTML/Elements/keygen
    - HTML/Elements/output
    - HTML/Elements/progress
    - HTML/Elements/meter
    - HTML/Elements/input/hidden
    - HTML/Elements/input/text
    - HTML/Elements/input/search
    - HTML/Elements/input/tel
    - HTML/Elements/input/url
    - HTML/Elements/input/email
    - HTML/Elements/input/password
    - HTML/Elements/input/datetime
    - HTML/Elements/input/date
    - HTML/Elements/input/month
    - HTML/Elements/input/week
    - HTML/Elements/input/time
    - HTML/Elements/input/datetime-local
    - HTML/Elements/input/number
    - HTML/Elements/input/range
    - HTML/Elements/input/color
    - HTML/Elements/input/checkbox
    - HTML/Elements/input/radio
    - HTML/Elements/input/file
    - HTML/Elements/input/submit
    - HTML/Elements/input/image
    - HTML/Elements/input/reset
    - HTML/Elements/input/button
    - 'HTML/Attributes/ Global'
uri: 'Meta:HTML/Elements/input'

---
**Needs Summary**: This article does not have a summary. Summaries give a brief overview of the topic and are automatically included on some listing pages that link to this article.

## Overview Table

[DOM Interface](/dom/interface)
:   [?](/w/index.php?title=%3F&action=edit&redlink=1)

-   [List of Elements](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
    -   [Forms](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
        -   [form](/w/index.php?title=HTML/Elements/form&action=edit&redlink=1)
        -   [fieldset](/w/index.php?title=HTML/Elements/fieldset&action=edit&redlink=1)
        -   [legend](/w/index.php?title=HTML/Elements/legend&action=edit&redlink=1)
        -   [label](/w/index.php?title=HTML/Elements/label&action=edit&redlink=1)
        -   [input](/w/index.php?title=HTML/Elements/input&action=edit&redlink=1)
        -   [button](/w/index.php?title=HTML/Elements/button&action=edit&redlink=1)
        -   [select](/w/index.php?title=HTML/Elements/select&action=edit&redlink=1)
        -   [datalist](/w/index.php?title=HTML/Elements/datalist&action=edit&redlink=1)
        -   [optgroup](/w/index.php?title=HTML/Elements/optgroup&action=edit&redlink=1)
        -   [option](/w/index.php?title=HTML/Elements/option&action=edit&redlink=1)
        -   [textarea](/w/index.php?title=HTML/Elements/textarea&action=edit&redlink=1)
        -   [keygen](/w/index.php?title=HTML/Elements/keygen&action=edit&redlink=1)
        -   [output](/w/index.php?title=HTML/Elements/output&action=edit&redlink=1)
        -   [progress](/w/index.php?title=HTML/Elements/progress&action=edit&redlink=1)
        -   [meter](/w/index.php?title=HTML/Elements/meter&action=edit&redlink=1)

# \<input\>

The \<input\> element represents a typed data field, usually with a form control to allow the user to edit the data.

## Point

-   The type attribute controls the data type (and associated control) of the element. It is an enumerated attribute.

-   The following table lists the keywords and states for the attribute.
    The keywords in the left column map to the states in the cell in the second column on the same row as the keyword.

|Keyword|State|Data type|Control type|
|:------|:----|:--------|:-----------|
|`hidden`|Hidden|An arbitrary string|n/a|
|`text`|Text|Text with no line breaks|Text field|
|`search`|Search|Text with no line breaks|Search field|
|`tel`|Telephone|Text with no line breaks|A text field|
|`url`|URL|An absolute IRI|A text field|
|`email`|E-mail|An e-mail address or list of e-mail addresses|A text field|
|`password`|Password|Text with no line breaks (sensitive information)|Text field that obscures data entry|
|`datetime`|Date and Time|A date and time (year, month, day, hour, minute, second, fraction of a second) with the time zone set to UTC|A date and time control|
|`date`|Date|A date (year, month, day) with no time zone|A date control|
|`month`|Month|A date consisting of a year and a month with no time zone|A month control|
|`week`|Week|A date consisting of a week-year number and a week number with no time zone|A week control|
|`time`|Time|A time (hour, minute, seconds, fractional seconds) with no time zone|A time control|
|`datetime-local`|Local Date and Time|A date and time (year, month, day, hour, minute, second, fraction of a second) with no time zone|A date and time control|
|`number`|Number|A numerical value|A text field or spinner control|
|`range`|Range|A numerical value, with the extra semantic that the exact value is not important|A slider control or similar|
|`color`|Color|An sRGB color with 8-bit red, green, and blue components|A color well|
|`checkbox`|Checkbox|A set of zero or more values from a predefined list|A checkbox|
|`radio`|Radio Button|An enumerated value|A radio button|
|`file`|File Upload|Zero or more files each with a MIME type and optionally a file name|A label and a button|
|`submit`|Submit Button|An enumerated value, with the extra semantic that it must be the last value selected and initiates form submission|A button|
|`image`|Image Button|A coordinate, relative to a particular image's size, with the extra semantic that it must be the last value selected and initiates form submission|Either a clickable image, or a button|
|`reset`|Reset Button|n/a|A button|
|`button`|Button|n/a|A button|

## HTML Attributes

-   Which of the attributes apply to an input element depends on the state of its type attribute. The following table is summarizes which of those content attributes.

<table class="filehistory">
<tr>
<th>
</th>
<th>
Hidden

</th>
<th>
Text, Search, URL, Telephone

</th>
<th>
E-mail

</th>
<th>
Password

</th>
<th>
Date and Time, Date, Month, Week, Time

</th>
<th>
Local Date and Time, Number

</th>
<th>
Range

</th>
<th>
Color

</th>
<th>
Checkbox, Radio Button

</th>
<th>
File Upload

</th>
<th>
Submit Button

</th>
<th>
Image Button

</th>
<th>
Reset Button, Button

</th>
</tr>
<tr>
<th colspan="14" scope="rowgroup">
Content attributes

</th>
</tr>
<tr>
<th>
`accept`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`alt`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`autocomplete`

</th>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`checked`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`formaction`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`formenctype`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`formmethod`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`formnovalidate`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`formtarget`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`height`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`list`

</th>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`max`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`maxlength`

</th>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`min`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`multiple`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`pattern`

</th>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`placeholder`

</th>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`readonly`

</th>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`required`

</th>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`size`

</th>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`src`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`step`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
</tr>
<tr>
<th>
`width`

</th>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="no">
·

</td>
<td class="yes">
Yes

</td>
<td class="no">
·

</td>
</tr>
</table>

See also [global attributes](/w/index.php?title=HTML/Attributes/_Global&action=edit&redlink=1).

## HTML Reference

The HTML5 specification defines the \<input\> element in [4.10.7 The input element](http://www.w3.org/TR/html5/the-input-element.html#the-input-element).

**Needs Examples**: This section should include examples.

