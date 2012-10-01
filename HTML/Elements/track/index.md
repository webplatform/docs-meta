{{Page_Title}}
{{Flags
|High-level issues=Merge Candidate
}}
{{Standardization_Status}}
{{API_Name}}
{{Summary_Section}}
{{Markup_Element
|Content=

<div style='float: right;background: white;border:1px dashed black;padding: 1ex;margin-left: 1ex;'>

* [[HTML/Elements|List of Elements]]
** [[HTML/Elements#Embedded_content|Embedded Content]]
*** [[HTML/Elements/img|img]]
*** [[HTML/Elements/iframe|iframe]]
*** [[HTML/Elements/embed|embed]]
*** [[HTML/Elements/object|object]]
*** [[HTML/Elements/param|param]]
*** [[HTML/Elements/video|video]]
*** [[HTML/Elements/audio|audio]]
*** [[HTML/Elements/source|source]]
*** [[HTML/Elements/track|track]]
*** [[HTML/Elements/canvas|canvas]]
*** [[HTML/Elements/map|map]]
*** [[HTML/Elements/area|area]]
*** [[HTML/Elements/math|math]]
*** [[HTML/Elements/svg|svg]]
*** [[HTML/Elements/applet|applet]]
*** [[HTML/Elements/frame|frame]]
*** [[HTML/Elements/frameset|frameset]]
*** [[HTML/Elements/noframes|noframes]]
*** [[HTML/Elements/bgsound|bgsound]]
*** [[HTML/Elements/noembed|noembed]]
*** [[HTML/Elements/plaintext|plaintext]]

</div>

= <track> =

The <track> element allows authors to specify explicit external timed tracks for media elements. It does not represent anything on its own.

== HTML Attributes ==

* <code>kind</code> = subtitles/ captions/ descriptions/ chapters/ metadata<br />
** <code>subtitles</code><br />Transcription or translation of the dialogue, suitable for when the sound is available but not understood
** <code>captions</code><br />Transcription or translation of the dialogue, sound effects, relevant musical cues, and other relevant audio information, suitable for when the soundtrack is unavailable
** <code>descriptions</code><br />Textual descriptions of the video component of the media resource, intended for audio synthesis when the visual component is unavailable 
** <code>chapters</code><br />Chapter titles, intended to be used for navigating the media resource.
** <code>metadatas</code><br />Tracks intended for use from script.


* <code>src</code> =  valid non-empty URL potentially surrounded by spaces<br />Gives the address of the timed track data.<br />This attribute must be present.


* <code>charset</code> = character encoding name


* <code>srclang</code> = valid [http://dev.w3.org/html5/spec/Overview.html#refsBCP47| BCP47] language tag.<br />Gives the language of the timed track data.<br />This attribute must be present if the element's kind attribute is in the subtitles state.


* <code>label</code> = string<br />Gives a user-readable title for the track.



See also [[HTML/Attributes/_Global|global attributes]].


== Examples ==

This video has subtitles in several languages:
<pre>
<video src="brave.webm">
 <track kind=subtitles src=brave.en.srt srclang=en label="English">
 <track kind=captions src=brave.en.srt srclang=en label="English for the Hard of Hearing">
 <track kind=subtitles src=brave.fr.srt srclang=fr label="Français">
 <track kind=subtitles src=brave.de.srt srclang=de label="Deutsch">
</video>
</pre>


== HTML reference ==

This element was introduced in HTML5 - [http://www.w3.org/TR/html5/the-iframe-element.html#the-track-element 4.8.9 The track element].


== See also ==

* [[HTML/Elements/audio|<code><audio></code>]]
* [[HTML/Elements/video|<code><video></code>]]

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
|MDN_link=
|MSDN_link=
|HTML5Rocks_link=
}}