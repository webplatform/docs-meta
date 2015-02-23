== Media Events ==

{| border="1"
!Event name
!Dispatched when...
|-
| <code>loadstart</code>
| The user agent begins looking for media data, as part of the resource selection algorithm.
|-
| <code>progress</code>
| The user agent is fetching media data.
|-
| <code>suspend</code>
| The user agent is intentionally not currently fetching media data, but does not have the entire media resource downloaded.
|-
| <code>abort</code>
| The user agent stops fetching the media data before it is completely downloaded, but not due to an error.
|-
| <code>error</code>
| An error occurs while fetching the media data.
|-
| <code>emptied</code>
| A media element whose <code>networkState</code> was previously not in the <code>NETWORK_EMPTY</code> state has just switched to that state (either because of a fatal error during load that's about to be reported, or because the <code>load()</code> method was invoked while the resource selection algorithm was already running).
|-
| <code>stalled</code>
| The user agent is trying to fetch media data, but data is unexpectedly not forthcoming.
|-
| <code>play</code>
| Playback has begun. Fired after the <code>play()</code> method has returned, or when the <code>autoplay</code> attribute has caused playback to begin.
|-
| <code>pause</code>
| Playback has been paused. Fired after the <code>pause()</code> method has returned.
|-
| <code>loadedmetadata</code>
| The user agent has just determined the duration and dimensions of the media resource
|-
| <code>loadeddata</code>
| The user agent can render the media data at the current playback position for the first time.
|-
| <code>waiting</code>
| Playback has stopped because the next frame is not available, but the user agent expects that frame to become available in due course.
|-
| <code>playing</code>
| Playback has started.
|-
| <code>canplay</code>
| The user agent can resume playback of the media data, but estimates that if playback were to be started now, the media resource could not be rendered at the current playback rate up to its end without having to stop for further buffering of content.
|-
| <code>canplaythrough</code>
| The user agent estimates that if playback were to be started now, the media resource could be rendered at the current playback rate all the way to its end without having to stop for further buffering.
|-
| <code>seeking</code>
| The <code>seeking</code> IDL attribute changed to true and the seek operation is taking long enough that the user agent has time to fire the event.
|-
| <code>seeked</code>
| The <code>seeking</code> IDL attribute changed to false.
|-
| <code>timeupdate</code>
| The current playback position changed as part of normal playback or in an especially interesting way, for example discontinuously.
|-
| <code>ended</code>
| Playback has stopped because the end of the media resource was reached.
|-
| <code>ratechange</code>
| Either the <code>defaultPlaybackRate</code> or the <code>playbackRate</code> attribute has just been updated.
|-
| <code>durationchange</code>
| The <code>duration</code> attribute has just been updated.
|-
| <code>volumechange</code>
| Either the <code>volume</code> attribute or the <code>muted</code> attribute has changed. Fired after the relevant attribute's setter has returned.
|}



== See also ==

# [http://html5doctor.com/native-audio-in-the-browser/ Audio in the browser]
# [http://9elements.com/io/projects/html5/canvas/ HTML5 Canvas and Audio Experiment]