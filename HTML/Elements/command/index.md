---
title: command
notes:
  - 'Can''t find a normative reference. Is this obsolete?'
overview_table:
  '[DOM Interface](/dom/interface)': '[[|]]'
standardization_status: Experimental
tags:
  - HTML
  - HTMLElement
  - Markup
  - Elements
todo_broken_links:
  note: 'During import MediaWiki could not find the following links, please fix and adjust this list.'
  links:
    - 'HTML/Attributes/ Global'
uri: 'Meta:HTML/Elements/command'

---
**Needs Summary**: This article does not have a summary. Summaries give a brief overview of the topic and are automatically included on some listing pages that link to this article.

## <span>Overview Table</span>

[DOM Interface](/dom/interface)
:   [[|]]

# <span>\<command\></span>

The \<command\> element represents a command that the user can invoke.

## <span>Point</span>

-   A command can be part of a context menu or toolbar, using the menu element, or can be put anywhere else in the page, to define a keyboard shortcut.

## <span>HTML Attributes</span>

-   `type` = command/ checkbox/ radio
    Indicates the kind of command:
    -   command
        Normal command with an associated action.
    -   checkbox
        State or option that can be toggled.
    -   radio
        Selection of one item from a list of items.

-   `label` = string
    Gives the name of the command, as shown to the user.
    The label attribute must be specified and must have a value that is not the empty string.

-   `icon` = valid non-empty URL potentially
    Gives a picture that represents the command.

-   `disabled` = boolean
    If present, indicates that the command is not available in the current state.

-   `checked` = boolean
    If present, indicates that the command is selected.
    The attribute must be omitted unless the type attribute is in either the Checkbox state or the Radio state.

-   `radiogroup` = string
    Gives the name of the group of commands that will be toggled when the command itself is toggled, for commands whose type attribute has the value "radio".

 See also [global attributes](/w/index.php?title=HTML/Attributes/_Global&action=edit&redlink=1).

Also, the title attribute has special semantics on this element.

## <span>Examples</span>

### <span>Example A</span>

[try it]:

    <menu type="toolbar">
      <command type="radio" radiogroup="alignment" checked="checked"
              label="Left" icon="icons/alL.png" onclick="setAlign('left')">
      <command type="radio" radiogroup="alignment"
              label="Center" icon="icons/alC.png" onclick="setAlign('center')">
      <command type="radio" radiogroup="alignment"
              label="Right" icon="icons/alR.png" onclick="setAlign('right')">
      <hr>
      <command type="command" disabled="disabled"
              label="Publish" icon="icons/pub.png" onclick="publish()">
    </menu>

## <span>HTML Reference</span>

The HTML5 specification defines the \<command\> element in [4.12.3 The command element](http://www.w3.org/TR/html5/interactive-elements.html#the-command-element).

**Needs Examples**: This section should include examples.

