---
title: optgroup
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
    - 'HTML/Attributes/ Global'
uri: 'Meta:HTML/Elements/optgroup'

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

# \<optgroup\>

The \<optgroup\> element represents a group of option elements with a common label.

## Point

-   The label attribute must be specified. [[Example A]](#Example_A)

## HTML Attributes

-   `disabled` = boolean
    if present, disable a group of option elements together.

-   `label` = string
    Its value gives the name of the group, for the purposes of the user interface.

 See [global attributes](/w/index.php?title=HTML/Attributes/_Global&action=edit&redlink=1).

## Examples

### Example A

[try it]:

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

## HTML Reference

The HTML5 specification defines the \<optgroup\> element in [4.10.11 The optgroup element](http://www.w3.org/TR/html5/the-button-element.html#the-optgroup-element).

**Needs Examples**: This section should include examples.

