---
title: ol
overview_table:
  '[DOM Interface](/dom/interface)': '[?](/w/index.php?title=%3F&action=edit&redlink=1)'
summary: 'The ol element makes an ordered list from the li (list item) elements it contains. Typically, each item is rendered with a number before it.'
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
    - 'HTML/Attributes/ Global'
uri: 'Meta:HTML/Elements/ol'

---
## <span>Summary</span>

The ol element makes an ordered list from the li (list item) elements it contains. Typically, each item is rendered with a number before it.

## <span>Overview Table</span>

[DOM Interface](/dom/interface)
:   [?](/w/index.php?title=%3F&action=edit&redlink=1)

-   [List of Elements](/Meta:HTML/Elements)
    -   [Grouping content](/Meta:HTML/Elements#Grouping_content)
        -   [p](/Meta:HTML/Elements/p)
        -   [hr](/Meta:HTML/Elements/hr)
        -   [pre](/Meta:HTML/Elements/pre)
        -   [blockquote](/Meta:HTML/Elements/blockquote)
        -   **ol**
        -   [ul](/Meta:HTML/Elements/ul)
        -   [li](/Meta:HTML/Elements/li)
        -   [dl](/Meta:HTML/Elements/dl)
        -   [dt](/Meta:HTML/Elements/dt)
        -   [dd](/Meta:HTML/Elements/dd)
        -   [figure](/Meta:HTML/Elements/figure)
        -   [figcaption](/Meta:HTML/Elements/figcaption)
        -   [div](/Meta:HTML/Elements/div)
        -   [center](/Meta:HTML/Elements/center)

# <span>\<ol\></span>

The \<ol\> element represents an *ordered list*. By default, most browsers add an integer as a marker before each list item:

1.  First list item
2.  Second list item
3.  Third list item

[[Example A]](#Example_A)

Use an ordered list where there's meaning to the order in which the list items appear. If the order is not important, it is more appropriate to use a [\<ul\>](/Meta:HTML/Elements/ul) unordered list element.

## <span>HTML Attributes</span>

-   `reversed`
    Renders numbers for the items in descending order list (...3, 2, 1), instead of the default ascending order (1, 2, 3...). [[Example B]](#Example_B)

-   `start` = valid integer
    Specifies the value for the first list item. [[Example C]](#Example_C)

-   `type` = the kind of marker
    Specifies the kind of marker to use in the list. [[Example D]](#Example_D)

<table>
<col width="50%" />
<col width="50%" />
<thead>
<tr class="header">
<th align="left"><pre><code>       Value</code></pre></th>
<th align="left"><pre><code>       Marker type</code></pre></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><pre><code>       1</code></pre></td>
<td align="left"><pre><code>       Default value Arabic numerals (1, 2, 3, 4)</code></pre></td>
</tr>
<tr class="even">
<td align="left"><pre><code>       a</code></pre></td>
<td align="left"><pre><code>       Lowercase roman letters in alphabetical ordered (a, b, c, d)</code></pre></td>
</tr>
<tr class="odd">
<td align="left"><pre><code>       A</code></pre></td>
<td align="left"><pre><code>       Uppercase roman letters in alphabetical order (A, B, C, D)</code></pre></td>
</tr>
<tr class="even">
<td align="left"><pre><code>       i</code></pre></td>
<td align="left"><pre><code>       Lowercase roman numerals numbers, lowercase (i, ii, iii, iv)</code></pre></td>
</tr>
<tr class="odd">
<td align="left"><pre><code>       I</code></pre></td>
<td align="left"><pre><code>       Uppercase roman numerals numbers, lowercase (I, II, III, IV)</code></pre></td>
</tr>
</tbody>
</table>

 See also [global attributes](/w/index.php?title=HTML/Attributes/_Global&action=edit&redlink=1).

## <span>Examples</span>

### <span>Example A</span>

[try it]

    <ol>
      <li>sample1</li>
      <li>sample2</li>
      <li>sample3</li>
    </ol>

[File:Ol01.png](/w/index.php?title=Special:Upload&wpDestFile=Ol01.png)

### <span>Example B</span>

With the reversed attribute [try it]:

    <ol reversed>
      <li>sample1</li>
      <li>sample2</li>
      <li>sample3</li>
    </ol>

[File:Li02.png](/w/index.php?title=Special:Upload&wpDestFile=Li02.png)

### <span>Example C</span>

With the start attribute [try it]:

    <ol start="101">
      <li>sample1</li>
      <li>sample2</li>
      <li>sample3</li>
    </ol>

[File:Ol03.png](/w/index.php?title=Special:Upload&wpDestFile=Ol03.png)

### <span>Example D</span>

With the type attribute [try it]:

    <ol type="lower-alpha">
      <li>sample1</li>
      <li>sample2</li>
      <li>sample3</li>
    </ol>

[File:Ol04.png](/w/index.php?title=Special:Upload&wpDestFile=Ol04.png)

## <span>HTML Reference</span>

The HTML5 specification defines the \<ol\> element in [4.5.5 The ol element](http://www.w3.org/TR/html5/grouping-content.html#the-ol-element).

## <span>See also</span>

-   [HTML Lists](/guides/html_lists)

**Needs Examples**: This section should include examples.

## <span>See also</span>

### <span>Related articles</span>

#### <span>HTML</span>

-   [user-modify](/css/properties/user-modify)

-   [HTMLAudioElement](/dom/HTMLAudioElement)

-   [textLength](/dom/HTMLTextAreaElement/textLength)

-   [value](/dom/HTMLTextAreaElement/value)

-   [accept](/html/attributes/accept)

-   [action](/html/attributes/action)

-   [alt](/html/attributes/alt)

-   [autocomplete](/html/attributes/autocomplete)

-   [autofocus](/html/attributes/autofocus)

-   [checked](/html/attributes/checked)

-   [crossorigin](/html/attributes/crossorigin)

-   [form](/html/attributes/form)

-   [formEnctype](/html/attributes/formEnctype)

-   [height](/html/attributes/height)

-   [list](/html/attributes/list)

-   [max (HTMLInputElement)](/html/attributes/max_(HTMLInputElement))

-   [maxLength](/html/attributes/maxLength)

-   [min](/html/attributes/min)

-   [multiple](/html/attributes/multiple)

-   [readonly](/html/attributes/readonly)

-   [size](/html/attributes/size)

-   [standby](/html/attributes/standby)

-   [step](/html/attributes/step)

-   [HTML Elements](/html/elements)

-   [!DOCTYPE](/html/elements/!DOCTYPE)

-   [!DOCTYPE](/html/elements/!DOCTYPE/ja)

-   [acronym](/html/elements/acronym)

-   [b](/html/elements/b)

-   [b](/html/elements/b/ja)

-   [br](/html/elements/br)

-   [br](/html/elements/br/ja)

-   [button](/html/elements/button)

-   [button](/html/elements/button/ja)

-   [caption](/html/elements/caption)

-   [cite](/html/elements/cite)

-   [code](/html/elements/code)

-   [col](/html/elements/col)

-   [colgroup](/html/elements/colgroup)

-   [datalist](/html/elements/datalist)

-   [del](/html/elements/del)

-   [dfn](/html/elements/dfn)

-   [div](/html/elements/div)

-   [em](/html/elements/em)

-   [EMBED](/html/elements/embed)

-   [fieldset](/html/elements/fieldset)

-   [font](/html/elements/font)

-   [footer](/html/elements/footer)

-   [head](/html/elements/head)

-   [hn](/html/elements/hn)

-   [hr](/html/elements/hr)

-   [html](/html/elements/html)

-   [i](/html/elements/i)

-   [img](/html/elements/img)

-   [input](/html/elements/input)

-   [ins](/html/elements/ins)

-   [kbd](/html/elements/kbd)

-   [legend](/html/elements/legend)

-   [mark](/html/elements/mark)

-   [option](/html/elements/option)

-   [p](/html/elements/p)

-   [samp](/html/elements/samp)

-   [script](/html/elements/script)

-   [span](/html/elements/span)

-   [strong](/html/elements/strong)

-   [table](/html/elements/table)

-   [tbody](/html/elements/tbody)

-   [td](/html/elements/td)

-   [tfoot](/html/elements/tfoot)

-   [th](/html/elements/th)

-   [time](/html/elements/time)
