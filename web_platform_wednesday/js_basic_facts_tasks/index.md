---
title: 'js basic facts tasks'
uri: 'Meta:web platform wednesday/js basic facts tasks'

---
### Compare the WPD page to the original Microsoft Developer Network article linked from the bottom of the page

If any content didn't make it through the import, add it to WPD page.

Example:

-   <http://docs.webplatform.org/wiki/javascript/Array>
-   <http://msdn.microsoft.com/en-us/library/ie/k4h76zbx(v=vs.94).aspx>

The Requirements section on MSDN were dropped.

Add them to the Import Notes section.

### Review all content in "Main content" field

If there are any constructor, properties, functions, or methods lists, compare them to the automatically generated one. Delete duplicates from the "Main content" field.

This "Main content" field will be removed after our review. Move any remaining content out of this field and to either Usage, Notes, or Import Notes.

### Compare the syntax values to the ones in the specification

Make sure all syntax variations are reflected.

Example:

-   <http://docs.webplatform.org/wiki/javascript/Array>
-   <http://www.ecma-international.org/ecma-262/5.1/#sec-15.4>

Under Section 15.4 of the spec:

-   the first syntax variation is when the Array Constructor is called as a function (15.4.1):
    -   `[ item1 [ , item2 [ , … ] ] ]`
-   the second variation is when the Array Constructor is called as part of a "new" expression (15.4.2). This variation takes 2 different kinds of parameters: items (15.4.2.1) and length (15.4.2.1), so show both:
    -   `new Array ( [ item0 [ , item1 [ , … ] ] ] )`
    -   `new Array (len)`

### Remove lefthand assignment from the parameters list

For example:

-   <http://docs.webplatform.org/wiki/javascript/Array>
-   <http://msdn.microsoft.com/en-us/library/ie/k4h76zbx(v=vs.94).aspx>

`arrayObj` is not a parameter of the Array Object.

If the description for that lefthand assignment provides additional information, such as what is returned, move that information to another, more appropriate, section.

Then, remove `arrayObj` from the list of parameters.

Move any return values to the Return Value section

### Add the specification to the WPD page

In the Manual sections, add a link to the spec

For example:

    ===Specification===
    [http://www.ecma-international.org/ecma-262/5.1/#sec-15.4 15.4 Array Objects]
    ECMAScript® Language Specification
    Standard ECMA-262
    5.1 Edition / June 2011

### Add the page type to the WPD page

In the form edit view, in the JavaScript Page section, select the page type.

For example, the Array page:

<http://docs.webplatform.org/w/index.php?title=javascript/Array&action=formedit>

Is a JS Object page
