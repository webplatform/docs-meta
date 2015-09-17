---
title: 'menu'
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
    - HTML/Elements/details
    - HTML/Elements/summary
    - HTML/Elements/command
    - HTML/Elements/menu
    - 'HTML/Attributes/ Global'
uri: 'Meta:HTML/Elements/menu'

---
**Needs Summary**: This article does not have a summary. Summaries give a brief overview of the topic and are automatically included on some listing pages that link to this article.

## Overview Table

[DOM Interface](/dom/interface)
:   [?](/w/index.php?title=%3F&action=edit&redlink=1)

-   [List of Elements](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
    -   [Interactive](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
        -   [details](/w/index.php?title=HTML/Elements/details&action=edit&redlink=1)
        -   [summary](/w/index.php?title=HTML/Elements/summary&action=edit&redlink=1)
        -   [command](/w/index.php?title=HTML/Elements/command&action=edit&redlink=1)
        -   [menu](/w/index.php?title=HTML/Elements/menu&action=edit&redlink=1)

# \<menu\>

The \<menu\> element represents a list of commands.

## HTML Attributes

-   `type` = context/ toolbar/ list
    Indicates the kind of menu being declared:
    -   context
        the commands of a context menu, and the user can only interact with the commands if that context menu is activated. [[Example B]](#Example_B)
    -   toolbar
        A list of active commands that the user can immediately interact with. [[Example A]](#Example_A)
    -   list
        an unordered list of items (each represented by an li element), each of which represents a command that the user can perform or activate, or, if the element has no li element children, flow content describing available commands.

-   `label` = string
    Gives the label of the menu.

 See also [global attributes](/w/index.php?title=HTML/Attributes/_Global&action=edit&redlink=1).

## Examples

### Example A

For example, the following represents a toolbar with three menu buttons on it, each of which has a dropdown menu with a series of options [try it]:

    <menu type="toolbar">
      <li>
        <menu label="File">
          <button type="button" onclick="fnew()">New...</button>
          <button type="button" onclick="fopen()">Open...</button>
          <button type="button" onclick="fsave()">Save</button>
          <button type="button" onclick="fsaveas()">Save as...</button>
        </menu>
      </li>
      <li>
        <menu label="Edit">
          <button type="button" onclick="ecopy()">Copy</button>
          <button type="button" onclick="ecut()">Cut</button>
          <button type="button" onclick="epaste()">Paste</button>
        </menu>
      </li>
      <li>
        <menu label="Help">
          <li><a href="help.html">Help</a></li>
          <li><a href="about.html">About</a></li>
        </menu>
      </li>
    </menu>

[File:Menu01.png](/w/index.php?title=Special:Upload&wpDestFile=Menu01.png)

### Example B

Here is an example of a context menu for an input control [try it]:

    <form name="npc">
      <label>Character name: <input name=char type=text contextmenu=namemenu required></label>
       <menu type=context id=namemenu>
         <command label="Pick random name"
            onclick="document.forms.npc.elements.char.value = getRandomName()">
         <command label="Prefill other fields based on name"
            onclick="prefillFields(document.forms.npc.elements.char.value)">
       </menu>
    </form>

## HTML Reference

The HTML5 specification defines the \<menu\> element in [4.12.4 The menu element](http://www.w3.org/TR/html5/interactive-elements.html#the-menu-element).

**Needs Examples**: This section should include examples.

