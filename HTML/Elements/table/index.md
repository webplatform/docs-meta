---
title: 'table'
compatibility:
  feature: table
  topic: html
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
    - HTML/Elements/table
    - HTML/Elements/caption
    - HTML/Elements/colgroup
    - HTML/Elements/col
    - HTML/Elements/tbody
    - HTML/Elements/thead
    - HTML/Elements/tfoot
    - HTML/Elements/tr
    - HTML/Elements/td
    - HTML/Elements/th
    - 'HTML/Attributes/ Global'
    - 'HTML tables'
uri: 'Meta:HTML/Elements/table'

---
**Needs Summary**: This article does not have a summary. Summaries give a brief overview of the topic and are automatically included on some listing pages that link to this article.

## Overview Table

[DOM Interface](/dom/interface)
:   [?](/w/index.php?title=%3F&action=edit&redlink=1)

-   [List of Elements](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
    -   [Tables](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
        -   [table](/w/index.php?title=HTML/Elements/table&action=edit&redlink=1)
        -   [caption](/w/index.php?title=HTML/Elements/caption&action=edit&redlink=1)
        -   [colgroup](/w/index.php?title=HTML/Elements/colgroup&action=edit&redlink=1)
        -   [col](/w/index.php?title=HTML/Elements/col&action=edit&redlink=1)
        -   [tbody](/w/index.php?title=HTML/Elements/tbody&action=edit&redlink=1)
        -   [thead](/w/index.php?title=HTML/Elements/thead&action=edit&redlink=1)
        -   [tfoot](/w/index.php?title=HTML/Elements/tfoot&action=edit&redlink=1)
        -   [tr](/w/index.php?title=HTML/Elements/tr&action=edit&redlink=1)
        -   [td](/w/index.php?title=HTML/Elements/td&action=edit&redlink=1)
        -   [th](/w/index.php?title=HTML/Elements/th&action=edit&redlink=1)

# \<table\>

The \<table\> element represents data with more than one dimension, in the form of a table.

## Point

-   Tables must not be used as layout aids. There are a variety of alternatives to using HTML tables for layout, primarily using CSS positioning and the CSS table model.
-   Users might have difficulty understanding the content, authors should include explanatory information introducing the table. This information is useful for all users, but is especially useful for users who cannot see the table, e.g. users of screen readers.[[Example B]](#Example_B)
-   Tables have rows and columns given by their descendants. A table must not have an empty row or column.

## HTML Attributes

-   `summary` = explanatory information introducing the table

See also [global attributes](/w/index.php?title=HTML/Attributes/_Global&action=edit&redlink=1).

## Examples

### Example A

[try it]:

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

[File:Table01.png](/w/index.php?title=Special:Upload&wpDestFile=Table01.png)

### Example B

The following example is including explanatory information introducing the table by next to the table in the same figure [try it]:

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

[File:Table02.png](/w/index.php?title=Special:Upload&wpDestFile=Table02.png)

## HTML Reference

The HTML5 specification defines the \<table\> element in [4.9.1 The table element](http://www.w3.org/TR/html5/tabular-data.html#the-table-element).

## See also

-   [HTML tables](/w/index.php?title=HTML_tables&action=edit&redlink=1)

**Needs Examples**: This section should include examples.

