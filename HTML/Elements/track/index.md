---
title: Meta:HTML/Elements/track
---
<h1><span class="mw-headline" id="track">track</span></h1>
<div class="editors-only">
<p><b>Needs Summary</b>:   This article does not have a summary. Summaries give a brief overview of the topic and are automatically included on some listing pages that link to this article. 
</p>
</div>
<p><br />
</p>
<h2><span class="mw-headline" id="Overview_Table">Overview Table</span></h2>
<table class="wikitable">
<tr>
<th> <a href="/wiki/dom/interface" title="dom/interface"> DOM Interface</a>
</th>
<td> <a href="/w/index.php?title=%3F&amp;action=edit&amp;redlink=1" class="new" title="? (page does not exist)">?</a>
</td></tr></table>
<div style="float: right;background: white;border:1px dashed black;padding: 1ex;margin-left: 1ex;">
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">List of Elements</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements (page does not exist)">Embedded Content</a>
<ul><li> <a href="/w/index.php?title=HTML/Elements/img&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/img (page does not exist)">img</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/iframe&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/iframe (page does not exist)">iframe</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/embed&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/embed (page does not exist)">embed</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/object&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/object (page does not exist)">object</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/param&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/param (page does not exist)">param</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/video&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/video (page does not exist)">video</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/audio&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/audio (page does not exist)">audio</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/source&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/source (page does not exist)">source</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/track&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/track (page does not exist)">track</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/canvas&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/canvas (page does not exist)">canvas</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/map&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/map (page does not exist)">map</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/area&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/area (page does not exist)">area</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/math&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/math (page does not exist)">math</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/svg&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/svg (page does not exist)">svg</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/applet&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/applet (page does not exist)">applet</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/frame&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/frame (page does not exist)">frame</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/frameset&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/frameset (page does not exist)">frameset</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/noframes&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/noframes (page does not exist)">noframes</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/bgsound&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/bgsound (page does not exist)">bgsound</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/noembed&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/noembed (page does not exist)">noembed</a></li>
<li> <a href="/w/index.php?title=HTML/Elements/plaintext&amp;action=edit&amp;redlink=1" class="new" title="HTML/Elements/plaintext (page does not exist)">plaintext</a></li></ul></li></ul></li></ul>
</div>
<h1><span class="mw-headline" id=".3Ctrack.3E">&lt;track&gt;</span></h1>
<p>The &lt;track&gt; element allows authors to specify explicit external timed tracks for media elements. It does not represent anything on its own.
</p>
<h2><span class="mw-headline" id="HTML_Attributes">HTML Attributes</span></h2>
<ul><li> <code>kind</code> = subtitles/ captions/ descriptions/ chapters/ metadata<br />
<ul><li> <code>subtitles</code><br />Transcription or translation of the dialogue, suitable for when the sound is available but not understood</li>
<li> <code>captions</code><br />Transcription or translation of the dialogue, sound effects, relevant musical cues, and other relevant audio information, suitable for when the soundtrack is unavailable</li>
<li> <code>descriptions</code><br />Textual descriptions of the video component of the media resource, intended for audio synthesis when the visual component is unavailable </li>
<li> <code>chapters</code><br />Chapter titles, intended to be used for navigating the media resource.</li>
<li> <code>metadatas</code><br />Tracks intended for use from script.</li></ul></li></ul>
<p><br />
</p>
<ul><li> <code>src</code> =  valid non-empty URL potentially surrounded by spaces<br />Gives the address of the timed track data.<br />This attribute must be present.</li></ul>
<p><br />
</p>
<ul><li> <code>charset</code> = character encoding name</li></ul>
<p><br />
</p>
<ul><li> <code>srclang</code> = valid [<a rel="nofollow" class="external free" href="http://dev.w3.org/html5/spec/Overview.html#refsBCP47">http://dev.w3.org/html5/spec/Overview.html#refsBCP47</a></li></ul>
<div class="editors-only">
<p><b>Needs Examples</b>:  This section should include examples. 
</p>
</div>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>

<!-- Saved in parser cache with key wpwiki:pcache:idhash:885-0!*!0!!*!*!*!esi=1 and timestamp 20150731181519 and revision id 5592
 -->
