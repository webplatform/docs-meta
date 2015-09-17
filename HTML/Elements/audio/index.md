---
title: 'audio'
uri: 'Meta:HTML/Elements/audio'

---
## Media Events

|Event name|Dispatched when...|
|:---------|:-----------------|
|`loadstart`|The user agent begins looking for media data, as part of the resource selection algorithm.|
|`progress`|The user agent is fetching media data.|
|`suspend`|The user agent is intentionally not currently fetching media data, but does not have the entire media resource downloaded.|
|`abort`|The user agent stops fetching the media data before it is completely downloaded, but not due to an error.|
|`error`|An error occurs while fetching the media data.|
|`emptied`|A media element whose `networkState` was previously not in the `NETWORK_EMPTY` state has just switched to that state (either because of a fatal error during load that's about to be reported, or because the `load()` method was invoked while the resource selection algorithm was already running).|
|`stalled`|The user agent is trying to fetch media data, but data is unexpectedly not forthcoming.|
|`play`|Playback has begun. Fired after the `play()` method has returned, or when the `autoplay` attribute has caused playback to begin.|
|`pause`|Playback has been paused. Fired after the `pause()` method has returned.|
|`loadedmetadata`|The user agent has just determined the duration and dimensions of the media resource|
|`loadeddata`|The user agent can render the media data at the current playback position for the first time.|
|`waiting`|Playback has stopped because the next frame is not available, but the user agent expects that frame to become available in due course.|
|`playing`|Playback has started.|
|`canplay`|The user agent can resume playback of the media data, but estimates that if playback were to be started now, the media resource could not be rendered at the current playback rate up to its end without having to stop for further buffering of content.|
|`canplaythrough`|The user agent estimates that if playback were to be started now, the media resource could be rendered at the current playback rate all the way to its end without having to stop for further buffering.|
|`seeking`|The `seeking` IDL attribute changed to true and the seek operation is taking long enough that the user agent has time to fire the event.|
|`seeked`|The `seeking` IDL attribute changed to false.|
|`timeupdate`|The current playback position changed as part of normal playback or in an especially interesting way, for example discontinuously.|
|`ended`|Playback has stopped because the end of the media resource was reached.|
|`ratechange`|Either the `defaultPlaybackRate` or the `playbackRate` attribute has just been updated.|
|`durationchange`|The `duration` attribute has just been updated.|
|`volumechange`|Either the `volume` attribute or the `muted` attribute has changed. Fired after the relevant attribute's setter has returned.|

## See also

1.  [Audio in the browser](http://html5doctor.com/native-audio-in-the-browser/)
2.  [HTML5 Canvas and Audio Experiment](http://9elements.com/io/projects/html5/canvas/)
