---
title: 'track'
compatibility:
  feature: track
  topic: html
overview_table:
  '[DOM Interface](/dom/interface)': '[?](/w/index.php?title=%3F&action=edit&redlink=1)'
tags:
  - Markup
  - Elements
  - HTML
todo_broken_links:
  note: 'During import MediaWiki could not find the following links, please fix and adjust this list.'
  links:
    - '?'
    - HTML/Elements
    - HTML/Elements/img
    - HTML/Elements/iframe
    - HTML/Elements/embed
    - HTML/Elements/object
    - HTML/Elements/param
    - HTML/Elements/video
    - HTML/Elements/audio
    - HTML/Elements/source
    - HTML/Elements/track
    - HTML/Elements/canvas
    - HTML/Elements/map
    - HTML/Elements/area
    - HTML/Elements/math
    - HTML/Elements/svg
    - HTML/Elements/applet
    - HTML/Elements/frame
    - HTML/Elements/frameset
    - HTML/Elements/noframes
    - HTML/Elements/bgsound
    - HTML/Elements/noembed
    - HTML/Elements/plaintext
uri: 'Meta:HTML/Elements/track'

---
**Needs Summary**: This article does not have a summary. Summaries give a brief overview of the topic and are automatically included on some listing pages that link to this article.

## Overview Table

[DOM Interface](/dom/interface)
:   [?](/w/index.php?title=%3F&action=edit&redlink=1)

-   [List of Elements](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
    -   [Embedded Content](/w/index.php?title=HTML/Elements&action=edit&redlink=1)
        -   [img](/w/index.php?title=HTML/Elements/img&action=edit&redlink=1)
        -   [iframe](/w/index.php?title=HTML/Elements/iframe&action=edit&redlink=1)
        -   [embed](/w/index.php?title=HTML/Elements/embed&action=edit&redlink=1)
        -   [object](/w/index.php?title=HTML/Elements/object&action=edit&redlink=1)
        -   [param](/w/index.php?title=HTML/Elements/param&action=edit&redlink=1)
        -   [video](/w/index.php?title=HTML/Elements/video&action=edit&redlink=1)
        -   [audio](/w/index.php?title=HTML/Elements/audio&action=edit&redlink=1)
        -   [source](/w/index.php?title=HTML/Elements/source&action=edit&redlink=1)
        -   [track](/w/index.php?title=HTML/Elements/track&action=edit&redlink=1)
        -   [canvas](/w/index.php?title=HTML/Elements/canvas&action=edit&redlink=1)
        -   [map](/w/index.php?title=HTML/Elements/map&action=edit&redlink=1)
        -   [area](/w/index.php?title=HTML/Elements/area&action=edit&redlink=1)
        -   [math](/w/index.php?title=HTML/Elements/math&action=edit&redlink=1)
        -   [svg](/w/index.php?title=HTML/Elements/svg&action=edit&redlink=1)
        -   [applet](/w/index.php?title=HTML/Elements/applet&action=edit&redlink=1)
        -   [frame](/w/index.php?title=HTML/Elements/frame&action=edit&redlink=1)
        -   [frameset](/w/index.php?title=HTML/Elements/frameset&action=edit&redlink=1)
        -   [noframes](/w/index.php?title=HTML/Elements/noframes&action=edit&redlink=1)
        -   [bgsound](/w/index.php?title=HTML/Elements/bgsound&action=edit&redlink=1)
        -   [noembed](/w/index.php?title=HTML/Elements/noembed&action=edit&redlink=1)
        -   [plaintext](/w/index.php?title=HTML/Elements/plaintext&action=edit&redlink=1)

# \<track\>

The \<track\> element allows authors to specify explicit external timed tracks for media elements. It does not represent anything on its own.

## HTML Attributes

-   `kind` = subtitles/ captions/ descriptions/ chapters/ metadata
    -   `subtitles`
        Transcription or translation of the dialogue, suitable for when the sound is available but not understood
    -   `captions`
        Transcription or translation of the dialogue, sound effects, relevant musical cues, and other relevant audio information, suitable for when the soundtrack is unavailable
    -   `descriptions`
        Textual descriptions of the video component of the media resource, intended for audio synthesis when the visual component is unavailable
    -   `chapters`
        Chapter titles, intended to be used for navigating the media resource.
    -   `metadatas`
        Tracks intended for use from script.

-   `src` = valid non-empty URL potentially surrounded by spaces
    Gives the address of the timed track data.
    This attribute must be present.

-   `charset` = character encoding name

-   `srclang` = valid [<http://dev.w3.org/html5/spec/Overview.html#refsBCP47>

**Needs Examples**: This section should include examples.

