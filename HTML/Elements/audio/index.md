---
title: Meta:HTML/Elements/audio
---
<h2><span class="mw-headline" id="Media_Events">Media Events</span></h2>
<table border="1">
<tr>
<th>Event name
</th>
<th>Dispatched when...
</th></tr>
<tr>
<td> <code>loadstart</code>
</td>
<td> The user agent begins looking for media data, as part of the resource selection algorithm.
</td></tr>
<tr>
<td> <code>progress</code>
</td>
<td> The user agent is fetching media data.
</td></tr>
<tr>
<td> <code>suspend</code>
</td>
<td> The user agent is intentionally not currently fetching media data, but does not have the entire media resource downloaded.
</td></tr>
<tr>
<td> <code>abort</code>
</td>
<td> The user agent stops fetching the media data before it is completely downloaded, but not due to an error.
</td></tr>
<tr>
<td> <code>error</code>
</td>
<td> An error occurs while fetching the media data.
</td></tr>
<tr>
<td> <code>emptied</code>
</td>
<td> A media element whose <code>networkState</code> was previously not in the <code>NETWORK_EMPTY</code> state has just switched to that state (either because of a fatal error during load that's about to be reported, or because the <code>load()</code> method was invoked while the resource selection algorithm was already running).
</td></tr>
<tr>
<td> <code>stalled</code>
</td>
<td> The user agent is trying to fetch media data, but data is unexpectedly not forthcoming.
</td></tr>
<tr>
<td> <code>play</code>
</td>
<td> Playback has begun. Fired after the <code>play()</code> method has returned, or when the <code>autoplay</code> attribute has caused playback to begin.
</td></tr>
<tr>
<td> <code>pause</code>
</td>
<td> Playback has been paused. Fired after the <code>pause()</code> method has returned.
</td></tr>
<tr>
<td> <code>loadedmetadata</code>
</td>
<td> The user agent has just determined the duration and dimensions of the media resource
</td></tr>
<tr>
<td> <code>loadeddata</code>
</td>
<td> The user agent can render the media data at the current playback position for the first time.
</td></tr>
<tr>
<td> <code>waiting</code>
</td>
<td> Playback has stopped because the next frame is not available, but the user agent expects that frame to become available in due course.
</td></tr>
<tr>
<td> <code>playing</code>
</td>
<td> Playback has started.
</td></tr>
<tr>
<td> <code>canplay</code>
</td>
<td> The user agent can resume playback of the media data, but estimates that if playback were to be started now, the media resource could not be rendered at the current playback rate up to its end without having to stop for further buffering of content.
</td></tr>
<tr>
<td> <code>canplaythrough</code>
</td>
<td> The user agent estimates that if playback were to be started now, the media resource could be rendered at the current playback rate all the way to its end without having to stop for further buffering.
</td></tr>
<tr>
<td> <code>seeking</code>
</td>
<td> The <code>seeking</code> IDL attribute changed to true and the seek operation is taking long enough that the user agent has time to fire the event.
</td></tr>
<tr>
<td> <code>seeked</code>
</td>
<td> The <code>seeking</code> IDL attribute changed to false.
</td></tr>
<tr>
<td> <code>timeupdate</code>
</td>
<td> The current playback position changed as part of normal playback or in an especially interesting way, for example discontinuously.
</td></tr>
<tr>
<td> <code>ended</code>
</td>
<td> Playback has stopped because the end of the media resource was reached.
</td></tr>
<tr>
<td> <code>ratechange</code>
</td>
<td> Either the <code>defaultPlaybackRate</code> or the <code>playbackRate</code> attribute has just been updated.
</td></tr>
<tr>
<td> <code>durationchange</code>
</td>
<td> The <code>duration</code> attribute has just been updated.
</td></tr>
<tr>
<td> <code>volumechange</code>
</td>
<td> Either the <code>volume</code> attribute or the <code>muted</code> attribute has changed. Fired after the relevant attribute's setter has returned.
</td></tr></table>
<p><br />
</p>
<h2><span class="mw-headline" id="See_also">See also</span></h2>
<ol><li> <a rel="nofollow" class="external text" href="http://html5doctor.com/native-audio-in-the-browser/">Audio in the browser</a></li>
<li> <a rel="nofollow" class="external text" href="http://9elements.com/io/projects/html5/canvas/">HTML5 Canvas and Audio Experiment</a></li></ol>

<!-- Saved in parser cache with key wpwiki:pcache:idhash:883-0!*!*!!*!*!*!esi=1 and timestamp 20150731181509 and revision id 100635
 -->
