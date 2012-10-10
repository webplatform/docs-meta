{{Page_Title}}
{{Flags
|High-level issues=Merge Candidate
}}
{{Standardization_Status}}
{{API_Name}}
{{Summary_Section|Style element contains style information for a document. Style information should go inside of this element, usually in the [[css|CSS]] language.}}
{{Markup_Element
|DOM_interface=dom/HTMLStyleElement
|Content={{Editorial/Merge_Candidate
|Other=html/elements/style
}}

<div style='float: right;background: white;border:1px dashed black;padding: 1ex;margin-left: 1ex;'>

* [[HTML/Elements|List of Elements]]
** [[HTML/Elements#Document_metadata|Document metadata]]
*** [[HTML/Elements/head|head]]
*** [[HTML/Elements/title|title]]
*** [[HTML/Elements/base|base]]
*** [[HTML/Elements/isindex|isindex]]
*** [[HTML/Elements/link|link]]
*** [[HTML/Elements/meta|meta]]
*** [[HTML/Elements/style|style]]

</div>

= &lt;style&gt; =

The &lt;style&gt; element allows authors to embed style information in their documents.


== HTML Attributes ==
*<code>media</code> = media-query list<br />Specifies which media the styles apply to.<br />The default, if the media attribute is omitted, is "all", meaning that by default styles apply to all media.


*<code>type</code> = A valid MIME type that designates a styling language.<br />Gives the styling language.<br />The default value for the type attribute, which is used if the attribute is absent, is "text/css".


*<code>scoped</code> = boolean<br />Indicates that the specified style information is meant to apply only to the style element’s parent element, and that element’s child nodes. Otherwise, the specified styles are meant to apply to the entire document. [[#Example_B|[Example B]]]


*Also, the title attribute has special semantics on this element.<br />The title attribute on style elements defines alternative style sheet sets. If the style element has no title attribute, then it has no title; the title attribute of ancestors does not apply to the style element.


See also [[HTML/Attributes/_Global|global attributes]].


== Example ==

=== Example A ===
The following document has its emphasis styled as bright red text rather than italics text, while leaving titles of works and Latin words in their default italics. It shows how using appropriate elements enables easier restyling of documents. [try it]:
<pre>
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
</pre>

[[File:Style01.png]]

=== Example B ===
In the following example, the style element influences only a p element in section element. [try it]:
<pre>
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
</pre>

The following example is use to present markup to user agents that don't support the scoped attribute. [try it]:
<pre>
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
</pre>

[[File:Style03.png]]

== HTML Reference ==

The HTML5 specification defines the &lt;style&gt; element in [http://www.w3.org/TR/html5/semantics.html#the-style-element 4.2.6 The style element].

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
|Sources=MDN
|MDN_link=https://developer.mozilla.org/en-US/docs/HTML/Element/style
|MSDN_link=
|HTML5Rocks_link=
}}