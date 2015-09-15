---
title: meter
overview_table:
  '[DOM Interface](/dom/interface)': '[?](/w/index.php?title=%3F&action=edit&redlink=1)'
tags:
  - Pages
  - with
  - broken
  - file
  - links
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
    - 'HTML/Attributes/ Global'
uri: 'Meta:HTML/Elements/meter'

---
**Needs Summary**: This article does not have a summary. Summaries give a brief overview of the topic and are automatically included on some listing pages that link to this article.

## <span>Overview Table</span>

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

# <span>\<meter\></span>

The \<meter\> element represents a scalar measurement within a known range, or a fractional value.

## <span>Point</span>

-   Example of meter:
    -   disk usage
    -   relevance of a query result
    -   fraction of a voting population to have selected a particular candidate ...

-   The meter element should not be used to indicate progress (as in a progress bar). For that role, HTML provides a separate progress element.

-   The meter element also does not represent a scalar value of arbitrary range — for example, it would be wrong to use this to report a weight, or height, unless there is a known maximum value. [[Example of bad usage]](#Example_of_bad_usage)

-   Authors are encouraged to include a textual representation of the gauge's state in the element's contents, for users of user agents that do not support the meter element.

## <span>HTML Attributes</span>

-   `value` = valid floating point numbers
    Specifies the value to have the gauge indicate as the "measured" value.
    The value attribute must be specified.

-   `min` = valid floating point numbers
    Specifies the lower bound of the range.

-   `max` = valid floating point numbers
    Specifies the upper bound

-   `low` = valid floating point numbers
    Specifies the range that is considered to be the "low" part.

-   `high` = valid floating point numbers
    Specifies the range that is considered to be the "high" part.

-   `optimum` = valid floating point numbers
    Gives the position that is "optimum":
    -   If that is higher than the "high" value then this indicates that the higher the value, the better
    -   if it's lower than the "low" mark then it indicates that lower values are better
    -   if it is in between then it indicates that neither high nor low values are good.

 See also [global attributes](/w/index.php?title=HTML/Attributes/_Global&action=edit&redlink=1).

## <span>Examples</span>

### <span>Example A</span>

The following examples show three gauges that would all be three-quarters full [try it]:

    Storage space usage: <meter value=6 max=8>6 blocks used (out of 8 total)</meter>
    Voter turnout: <meter value=0.75><img alt="75%" src="graph75.png"></meter>
    Tickets sold: <meter min="0" max="100" value="75"></meter>

[File:Meter01.png](/w/index.php?title=Special:Upload&wpDestFile=Meter01.png)

### <span>Example B</span>

There is no explicit way to specify units in the meter element, but the units may be specified in the title attribute in free-form text [try it]:

    <dl>
      <dt>Radius: <dd> <meter min=0 max=20 value=12 title="centimeters">12cm</meter>
      <dt>Height: <dd> <meter min=0 max=10 value=2 title="centimeters">2cm</meter>
    </dl>

### <span><span style="color:#9c0037;">Example of bad usage</span></span>

The following example is incorrect use of the element, because it doesn't give a range (and since the default maximum is 1, both of the gauges would end up looking maxed out)

``` {style="color:gray;"}
<!-- do not copy this example, it is an example of bad usage! -->
<p>The grapefruit pie had a radius of <meter value=12>12cm</meter>
and a height of <meter value=2>2cm</meter>.</p>
```

## <span>HTML Reference</span>

The HTML5 specification defines the \<meter\> element in [4.10.17 The meter element](http://www.w3.org/TR/html5/the-button-element.html#the-meter-element).

**Needs Examples**: This section should include examples.

