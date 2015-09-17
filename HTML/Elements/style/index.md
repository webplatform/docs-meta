---
title: 'style'
attributions:
  - 'Mozilla Developer Network [![cc-by-sa-small-wpd.svg](/assets/thumb/8/8c/cc-by-sa-small-wpd.svg/120px-cc-by-sa-small-wpd.svg.png)](http://creativecommons.org/licenses/by-sa/3.0/us/): [Article](https://developer.mozilla.org/en-US/docs/HTML/Element/style)'
overview_table:
  '[DOM Interface](/dom/interface)': '[HTMLStyleElement](/dom/HTMLStyleElement)'
summary: 'Style element contains style information for a document. Style information should go inside of this element, usually in the CSS language.'
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
    - HTML/Elements
    - HTML/Elements/head
    - HTML/Elements/title
    - HTML/Elements/base
    - HTML/Elements/isindex
    - HTML/Elements/link
    - HTML/Elements/meta
    - HTML/Elements/style
    - 'HTML/Attributes/ Global'
uri: 'Meta:HTML/Elements/style'

---
## Summary

Style element contains style information for a document. Style information should go inside of this element, usually in the CSS language.

## Overview Table

[DOM Interface](/dom/interface)
:   [HTMLStyleElement](/dom/HTMLStyleElement)

**Merge Candidate**: This page is a candidate for merge with the following pages: [html/elements/style](/html/elements/style)

-   [List of Elements](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
    -   [Document metadata](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
        -   [head](/w/index.php?title=HTML/Elements/head&action=edit&redlink=1)
        -   [title](/w/index.php?title=HTML/Elements/title&action=edit&redlink=1)
        -   [base](/w/index.php?title=HTML/Elements/base&action=edit&redlink=1)
        -   [isindex](/w/index.php?title=HTML/Elements/isindex&action=edit&redlink=1)
        -   [link](/w/index.php?title=HTML/Elements/link&action=edit&redlink=1)
        -   [meta](/w/index.php?title=HTML/Elements/meta&action=edit&redlink=1)
        -   [style](/w/index.php?title=HTML/Elements/style&action=edit&redlink=1)

# \<style\>

The \<style\> element allows authors to embed style information in their documents.

## HTML Attributes

-   `media` = media-query list
    Specifies which media the styles apply to.
    The default, if the media attribute is omitted, is "all", meaning that by default styles apply to all media.

-   `type` = A valid MIME type that designates a styling language.
    Gives the styling language.
    The default value for the type attribute, which is used if the attribute is absent, is "text/css".

-   `scoped` = boolean
    Indicates that the specified style information is meant to apply only to the style element’s parent element, and that element’s child nodes. Otherwise, the specified styles are meant to apply to the entire document. [[Example B]](#Example_B)

-   Also, the title attribute has special semantics on this element.
    The title attribute on style elements defines alternative style sheet sets. If the style element has no title attribute, then it has no title; the title attribute of ancestors does not apply to the style element.

 See also [global attributes](/w/index.php?title=HTML/Attributes/_Global&action=edit&redlink=1).

## Example

### Example A

The following document has its emphasis styled as bright red text rather than italics text, while leaving titles of works and Latin words in their default italics. It shows how using appropriate elements enables easier restyling of documents. [try it]:

    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="utf-8">
        <title>My favorite book</title>
        <style>
           body { color: black; background: white; }
           em { font-style: normal; color: red; }
        </style>
      </head>
      <body>
        <p>My <em>favorite</em> book of all time has <em>got</em> to be
        <cite>A Cat's Life</cite>. It is a book by P. Rahmel that talks
        about the <i lang="la">Felis Catus</i> in modern human society.</p>
      </body>
    </html>

[File:Style01.png](/w/index.php?title=Special:Upload&wpDestFile=Style01.png)

### Example B

In the following example, the style element influences only a p element in section element. [try it]:

    <p>text</p>
    <section id="example1">
      <style scoped="scoped">
        p {
          color: #ff0000;
        }
      </style>
      <h1>title</h1>
      <p>text</p>
    </section>

The following example is use to present markup to user agents that don't support the scoped attribute. [try it]:

    <p>text</p>
    <section id="example1">
      <style scoped="scoped">
        #example1 p {
          color: #ff0000;
        }
      </style>
      <h1>title</h1>
      <p>text</p>
    </section>

[File:Style03.png](/w/index.php?title=Special:Upload&wpDestFile=Style03.png)

## HTML Reference

The HTML5 specification defines the \<style\> element in [4.2.6 The style element](http://www.w3.org/TR/html5/semantics.html#the-style-element).

**Needs Examples**: This section should include examples.

