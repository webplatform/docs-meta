---
title: Meta:Meta:tutorials anim transitions
---
<h1><span class="mw-headline" id="Dynamic_visual_effects_with_CSS3_transitions">Dynamic visual effects with CSS3 transitions</span></h1>
<p><b>By Mike Sierra</b><br />
</p>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>CSS transitions offer the easiest way to animate an
interface.  CSS is used everywhere to control how web pages appear,
and shifts from one set of style sheets to another ordinarily occur
abruptly.  Adding transition properties allows most of those changes
to occur gradually, for a more vibrant, fluid interface.
</p><p>This tutorial introduces CSS's various transition properties and shows
you how to control how smoothly transitions execute. It shows you how
to create sequences of more than one transition, but increasingly
complex movements require <a href="/wiki/tutorials/css_animations" title="tutorials/css animations">keyframe
animations</a>, which work similarly.  You should become familiar with
what CSS <i>transitions</i> can do before mastering <i>animations</i>.  Both
kinds of CSS-based animation require none of the JavaScript timers
traditionally used to move things around, and they execute much
faster.
</p><p>While transitions allow you to apply hover effects and other
relatively marginal enhancements to traditional desktop interfaces,
they are particularly useful for small-screen mobile interfaces in
which displaying elements need to slide or fade out of view, or else
collapse into icons. Abrupt transitions can be particularly
disorienting on a small screen.
</p><p>These key points serve as reference:
</p>
<ul><li> Transitions are simple animations that smooth shifts from one style sheet to another.</li></ul>
<ul><li> Set <a href="/wiki/css/properties/transition-property" title="css/properties/transition-property"><b>transition-property</b></a> to specify which CSS property (or <b>all</b>) to animate between style sheets.</li></ul>
<ul><li> Properties that reference numeric measurements and color values can be transitioned.</li></ul>
<ul><li> The <a href="/wiki/css/properties/transition-duration" title="css/properties/transition-duration"><b>transition-duration</b></a> property sets how much time the transition takes to run.</li></ul>
<ul><li> Use <a href="/wiki/css/properties/transition-delay" title="css/properties/transition-delay"><b>transition-delay</b></a> to pause before executing a transition.</li></ul>
<ul><li> Use comma-delimited values to apply more than one transition to an element, useful in building sequences.  Transitions can also execute concurrently when applied to different elements.</li></ul>
<ul><li> The <a href="/wiki/css/properties/transition-timing-function" title="css/properties/transition-timing-function"><b>transition-timing-function</b></a> property allows you to control a transitions's speed of progress.  It accepts keywords: <b>ease</b>, <b>ease-in</b>, <b>ease-out</b>, <b>ease-in-out</b>, <b>linear</b>, or custom <b>cubic-bezier()</b> response curves.</li></ul>
<ul><li> The <a href="/wiki/css/properties/transition" title="css/properties/transition"><b>transition</b></a> shorthand property can represent values from all other transition properties. If two time measurements are included, they are interpreted first as duration then as delay.</li></ul>
<ul><li> Specify a redundant set of property names prefixed <i>-webkit-</i>.</li></ul>
<ul><li> The <b>transitionend</b> event (or <b>webkitTransitionEnd</b>) fires at the end of a transition for each property that animates.</li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="The_transition_property">The transition property</span></h2>
<p>For transitions to work, there need to be two sets of style sheets
that might apply to any element as users interact with the page. In
this case, tapping a small <b>nav</b> element expands it out to a wider
navigation panel:
</p><p><a href="/wiki/File:transit_parent.png" class="image"><img alt="transit parent.png" src="//static.webplatform.org/w/public/f/f1/transit_parent.png" width="339" height="162" /></a>
</p><p>To achieve this effect, a default style sheet defines most of how it
appears. A second style sheet changes how it appears when it is
assigned the <i>expanded</i> class.
</p>
<pre>nav {
        /* transition applies to all varying elements */
    transition           &#160;: all 0.5s;
        /* dimensions and position (mostly outside view) */
    height               &#160;: 42px;
    width                &#160;: 300px;
    position             &#160;: absolute;
    right                &#160;: -260px;
    top                  &#160;: 10px;
    padding              &#160;: 2px;
    overflow             &#160;: hidden;
    box-sizing           &#160;: border-box;
        /* define icon */
    background-image     &#160;: url(html5.png);
    background-position-x&#160;: left;
    background-position-y&#160;: 50%;
    background-repeat    &#160;: no-repeat;
    background-size      &#160;: contain;
    background-color     &#160;: #fff;
        /* border and shadow hidden by default */
    border               &#160;: transparent solid medium;
    border-radius        &#160;: 4px;
    box-shadow           &#160;: 0 0 1em transparent;
}
nav.expanded  {
        /* transition applies to these varying elements */
    right                &#160;: 10px;   /* bring panel into view */
    background-position-x&#160;: 400px;  /* icon out of view */
    border               &#160;: #aaa solid medium;
    box-shadow           &#160;: 0 0 1em #777;
}
</pre>
<p>The <i>expanded</i> class specifies a handful of CSS properties that
override those that apply without the class.  Adding the
<a href="/wiki/css/properties/transition" title="css/properties/transition"><b>transition</b></a> property makes those
properties animate when toggling the class:
</p>
<pre>-moz-transition   &#160;: all 0.5s;
-o-transition     &#160;: all 0.5s;
-webkit-transition&#160;: all 0.5s;
transition        &#160;: all 0.5s;
</pre>
<p>Changes to the values of the <a href="/wiki/css/properties/right" title="css/properties/right"><b>right</b></a> and
<a href="/wiki/css/properties/background-position" title="css/properties/background-position"><b>background-position</b></a>
properties makes the element and its displaying icon slide in from the
right. As it does, the border and shadow appear and get darker.
</p><p><b>Note:</b> Though transition properties were implemented recently
enough, all browser engines but WebKit support them without <i>vendor</i>
prefixes<i> such as <b>-moz-</b>, <b>-o-</b>, or <b>-webkit-</b> as shown</i>
above. Still, you need prefixes to support older browser versions.
Further examples only show un-prefixed transition property names, but
for widest support you should apply all of them.
</p><p>The <a href="/wiki/css/properties/transition" title="css/properties/transition"><b>transition</b></a> property specifies
which properties to animate, <b>all</b> in this case, and the half
second the animation takes to execute.  It is shorthand for these
separate properties:
</p>
<pre>transition-property&#160;: all;
transition-duration&#160;: 0.5s;
transition-duration&#160;: 500ms; /* same as above, but expressed as milliseconds */
</pre>
<p>To see the animation in action, all you need is a mechanism to apply
the <i>expanded</i> class, in this case a <b>click</b> handler that also
responds to touch input:
</p>
<pre>document.querySelector('nav').addEventListener('click', function(event) {
    event.currentTarget.classList.toggle('expanded');
});
</pre>
<p>You'll notice that transitions respond very gracefully by reversing
direction if you re-toggle the class while the animation is executing.
</p>
<h2><span class="mw-headline" id="Parallel_transitions">Parallel transitions</span></h2>
<p>We want the panel to display a set of nested navigation icons, in this
case a set of horizontal <b>div</b> elements. A second
<a href="/wiki/css/properties/transition" title="css/properties/transition"><b>transition</b></a> property animates these
nested elements depending on the state of their parent <b>nav</b>
element:
</p>
<pre>nav &gt; div {
    transition       &#160;: all 0.5s;
    height           &#160;: 34px;
    width            &#160;: 34px;
    background-size  &#160;: contain;
    display          &#160;: inline-block; /* arranged horizontally */
    opacity          &#160;: 0;            /* faded */
    transform        &#160;: scale(0);     /* scaled down */
}
nav.expanded &gt; div {
    opacity          &#160;: 1;
    transform        &#160;: scale(1);
}
</pre>
<p>The <a href="/wiki/css/properties/opacity" title="css/properties/opacity"><b>opacity</b></a> property fades the icons,
and <a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> grows or shrinks them
down to a point. (See the <a href="/wiki/tutorials/css_transforms" title="tutorials/css transforms">tutorial on
CSS transforms</a> for details.)  Combined, the two sets of transitions
execute simultaneously:
</p>
<div class="MediaTransformError" style="width: 280px; height: 568px; display:inline-block;">Error creating thumbnail: File missing</div>
<p>For an element to be transitioned, it must specify a numeric value or
percentage, such as a measurement or set of coordinates, or values
that translate to numeric values, such as colors. Many keyword values
work as well, such as the color <b>red</b> or <b>center</b> when used as
a coordinate.  But you cannot transition properties whose values
specify a different kind of behavior. For example, you cannot
transition between the <a href="/wiki/css/properties/display" title="css/properties/display"><b>display</b></a>
property's <b>block</b> and <b>none</b> values, or use
<a href="/wiki/css/properties/text-align" title="css/properties/text-align"><b>text-align</b></a> to switch between
<b>left</b> and <b>right</b> justification.
</p><p><b>Note:</b> Generated content can be transitioned, but only by
separately styling
<a href="/w/index.php?title=before%27%27%27&amp;action=edit&amp;redlink=1" class="new" title="before''' (page does not exist)">before</a> and
<a href="/w/index.php?title=after%27%27%27&amp;action=edit&amp;redlink=1" class="new" title="after''' (page does not exist)">after</a> selectors.
</p>
<h2><span class="mw-headline" id="Sequential_transitions">Sequential transitions</span></h2>
<p>You are not limited to a single set of transitions to get from one set
of style sheets to another. The panel in this example first grows to
its full width, then lengthens. The sequence is then reversed when
collapsing the panel back down to icon size:
</p>
<div class="MediaTransformError" style="width: 900px; height: 253px; display:inline-block;">Error creating thumbnail: File missing</div>
<p>Here is the relevant CSS:
</p>
<pre>div {
    width              &#160;: 56px;
    height             &#160;: 56px;
    transition-property&#160;: height , width;  /* collapse sequence */
    transition-duration&#160;: 0.5s   , 0.5s;
    transition-delay   &#160;: 0.0s   , 0.5s;   /* delay 2nd transition */
}
div.expanded {
    transition-property&#160;: width  , height; /* expand sequence */
    width              &#160;: 280px;
    height             &#160;: 400px;
}
</pre>
<p>Each transition property uses commas to delimit additional transitions
that form the larger second-long sequence. In this case, the duration
for each is the same: half a second. The
<a href="/wiki/css/properties/transition-delay" title="css/properties/transition-delay"><b>transition-delay</b></a> property
specifies that the first executes immediately, but the second waits
until the first is complete.
</p><p>This example also specifies individual property names rather than
<b>all</b>. When transitioning to the <i>expanded</i> class, the
<a href="/wiki/css/properties/width" title="css/properties/width"><b>width</b></a> animates before the
<a href="/wiki/css/properties/height" title="css/properties/height"><b>height</b></a>, and the sequence reverses in
the other direction.
</p><p>The <a href="/wiki/css/properties/transition" title="css/properties/transition"><b>transition</b></a> shorthand property
also accommodates additional transitions. Here is the same as above,
but expressed more tersely:
</p>
<pre>div          { transition: height 0.5s 0.0s , width  0.5s 0.5s&#160;; }
div.expanded { transition: width  0.5s 0.0s , height 0.5s 0.5s&#160;; }
</pre>
<p>The first supplied time value is interpreted as the
<a href="/wiki/css/properties/transition-duration" title="css/properties/transition-duration"><b>transition-duration</b></a>, and the second as the
<a href="/wiki/css/properties/transition-delay" title="css/properties/transition-delay"><b>transition-delay</b></a>.
</p><p>Note that with no delay specified, you can use more than one
transition to animate selected properties simultaneously, which might
be useful if you want to animate some properties but not <b>all</b> of
them. You can also stagger the delays so that execution overlaps.  In
this example, a single transition specifies the
<a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> property to move six
cards to the right over the course of one second, but the delay for
each is successively staggered up to half a second so that the overall
sequence takes 1.5 seconds to execute:
</p>
<pre>section &gt; div {
    transition: transform 1s;
    transform: translateX(0px);
    /* ^^^ this transform is optional; transition assumes default value */
}
section.deal &gt; div {
    transform: translateX(300px); /* move to right */
}
section &gt; div:nth-of-type(6) {
    transition-delay: 0.0s;
    background-image: url(QueenSpade.png);
}
section &gt; div:nth-of-type(5) {
    transition-delay: 0.1s;
    background-image: url(KingClub.jpeg);
}
section &gt; div:nth-of-type(4) {
    transition-delay: 0.2s;
    background-image: url(JackClub.jpeg);
}
section &gt; div:nth-of-type(3) {
    transition-delay: 0.3s;
    background-image: url(AceSpade.jpeg);
}
section &gt; div:nth-of-type(2) {
    transition-delay: 0.4s;
    background-image: url(JackSpade.jpeg);
}
section &gt; div:nth-of-type(1) {
    transition-delay: 0.5s;
    background-image: url(JackHeart.jpeg);
}
</pre>
<p>The overall movement is staggered like this:
</p><p><a href="/wiki/File:transit_delay.png" class="image"><img alt="transit delay.png" src="//static.webplatform.org/w/public/5/51/transit_delay.png" width="389" height="298" /></a>
</p><p><span id="timing"></span>
</p>
<h2><span class="mw-headline" id="Timing_functions">Timing functions</span></h2>
<p>You may notice in the example above that the cards are not evenly
spaced. That's because transitions by default start out slowly, gather
speed, then slow down again at the end.  The
<a href="/wiki/css/properties/transition-timing-function" title="css/properties/transition-timing-function"><b>transition-timing-function</b></a>
property specifies this behavior. By default it uses an <b>ease</b>
value. If it were <b>linear</b>, they would all start and stop abruptly
and move at the same speed:
</p><p><a href="/wiki/File:transit_linear.png" class="image"><img alt="transit linear.png" src="//static.webplatform.org/w/public/9/95/transit_linear.png" width="331" height="297" /></a>
</p><p>Browsers represent these keywords as bezier curves, which makes their
response easier to visualize.  Here is the basic set of keyword values
along with their alternate <b>cubic-bezier()</b> functions.  The
animation's elapsed time and progress correspond to <i>x</i> and <i>y</i>
axes, so the more the line curves vertically along the way, the faster
the animation proceeds:
</p>
<div style="display:inline-block">
<p><a href="/wiki/File:transitF_linear.png" class="image"><img alt="transitF linear.png" src="//static.webplatform.org/w/public/8/8e/transitF_linear.png" width="338" height="338" /></a> <br />
<b>linear</b> <br /> <b>cubic-bezier(0.0, 0.0, 1.0, 1.0)</b>
</p>
</div>
<div style="display:inline-block">
<p><a href="/wiki/File:transitF_ease.png" class="image"><img alt="transitF ease.png" src="//static.webplatform.org/w/public/7/73/transitF_ease.png" width="335" height="335" /></a> <br />
<b>ease</b> <br /> <b>cubic-bezier(0.25, 0.1, 0.25, 1.0)</b>
</p>
</div>
<div style="display:inline-block">
<p><a href="/wiki/File:transitF_easeinout.png" class="image"><img alt="transitF easeinout.png" src="//static.webplatform.org/w/public/6/67/transitF_easeinout.png" width="345" height="345" /></a> <br />
<b>ease-in-out</b> <br /> <b>cubic-bezier(0.42, 0, 0.58, 1.0)</b>
</p>
</div>
<div style="display:inline-block">
<p><a href="/wiki/File:transitF_easein.png" class="image"><img alt="transitF easein.png" src="//static.webplatform.org/w/public/6/64/transitF_easein.png" width="342" height="342" /></a> <br />
<b>ease-in</b> <br /> <b>cubic-bezier(0.42, 0, 1.0, 1.0)</b>
</p>
</div>
<div style="display:inline-block">
<p><a href="/wiki/File:transitF_easeout.png" class="image"><img alt="transitF easeout.png" src="//static.webplatform.org/w/public/0/00/transitF_easeout.png" width="344" height="344" /></a> <br />
<b>ease-out</b> <br /> <b>cubic-bezier(0, 0, 0.58, 1.0)</b>
</p>
</div>
<p>This useful <a rel="nofollow" class="external text" href="http://cssglue.com/cubic">cubic bezier function utility</a>
allows you to create your own custom curve and the see the result
applied to various animations.
</p><p>Timing functions can also be specified as part of the
<a href="/wiki/css/properties/transition" title="css/properties/transition"><b>transition</b></a> shorthand
property. This example makes a sequence of two <b>ease-in</b> and
<b>ease-out</b> transitions resemble the behavior of a single
<b>ease-in-out</b> function:
</p>
<pre>div          { transition: height 0.5s 0.0s ease-in, width  0.5s 0.5s ease-out; }
div.expanded { transition: width  0.5s 0.0s ease-in, height 0.5s 0.5s ease-out; }
</pre>
<p>As an alternative to response curves, the <b>steps()</b> function
specifies a series of distinct frames with no smoothing applied. This
animates three interim steps that occur between the start and end
points:
</p>
<pre>transition-timing-function&#160;: steps(5);
</pre>
<h2><span class="mw-headline" id="The_transitionend_event">The transitionend event</span></h2>
<p>The <b>transitionend</b> event allows an application to respond after a
transition finishes executing.  The event fires on the element that is
being transitioned, once for each property, and <i>only</i> if the
specified transition actually modifies content.
</p><p>In this example, applying a <i>display</i> class makes an information
panel appear:
</p><p><a href="/wiki/File:transit_end.png" class="image"><img alt="transit end.png" src="//static.webplatform.org/w/public/1/13/transit_end.png" width="396" height="147" /></a>
</p><p>The <a href="/wiki/css/properties/opacity" title="css/properties/opacity"><b>opacity</b></a> property makes the
element fade in, and is the only noticable change to its appearance. A
second transition executes over a longer span of time, and makes an
imperceptible change to the background color. Here is the relevant
CSS:
</p>
<pre>div {
    background-color&#160;: white;
    opacity         &#160;: 0;
    transition      &#160;: opacity 1s, background-color 5s;
}
div.display {
    opacity         &#160;: 1;
    background-color&#160;: rgba(100%, 100%, 100%, 0.95);
}
</pre>
<p>After 5 seconds, a <b>transitionend</b> handler removes the <i>display</i>
class to revert the element back to its original state:
</p>
<pre>var panel = document.querySelector('.message');
panel.addEventListener('transitionend'       , timeoutDisplay); // Standard: Gecko, IE10, Opera 12.10+
panel.addEventListener('otransitionend'      , timeoutDisplay); // Old Opera
panel.addEventListener('webkitTransitionEnd' , timeoutDisplay); // WebKit

function timeoutDisplay(e) {
    // ignore irrelevant transitions:
    if (e.propertyName&#160;!= 'background-color') return(false);
    // execute only after expanding panel:
    if (! e.currentTarget.classList.contains('display')) return(false);
    // collapse panel:
    e.currentTarget.classList.remove('display');
}
</pre>
<p>Note the various provisional names for the event:
<b>webkitTransitionEnd</b> (WebKit), <b>otransitionend</b> (old Opera),
along with the standard <b>transitionend</b> (Gecko, Opera 12.10+,
Internet Explorer).
</p><p><span id="advanced"></span>
</p>
<h2><span class="mw-headline" id="Advanced_image_transitions">Advanced image transitions</span></h2>
<p>While it's pretty obvious which properties can be transitioned, some
browsers are adding support for a couple of unusual ones. So far these
non-standard features can only be found in Webkit browsers.
</p><p>Transitions between two
<a href="/wiki/css/properties/background-image" title="css/properties/background-image"><b>background-image</b></a> files now
results in a cross-fade effect. Changing style sheets such as the
following can thus drive an image gallery interface:
</p>
<pre>div[data-img="4"] { background-image&#160;: url("Image04.jpg"); }
div[data-img="5"] { background-image&#160;: url("Image05.jpg"); }
</pre>
<p><a href="/wiki/File:fade.png" class="image"><img alt="fade.png" src="//static.webplatform.org/w/public/1/1e/fade.png" width="1009" height="293" /></a>
</p><p>See the <a href="/wiki/css/functions/cross-fade" title="css/functions/cross-fade">cross-fade()</a> function for a way
to mix images statically.
</p><p><b>Note:</b> As of this writing, there is no support for transitions
between <a href="/wiki/css/functions/linear-gradient" title="css/functions/linear-gradient">gradient</a> background image
values.
</p><p>The <a href="/wiki/css/properties/filter" title="css/properties/filter"><b>filter</b></a> property allows you to
apply sequences of image processing functions to any kind of visual
element, and these effects can also be transitioned. This more unusual
example applies a transition to a video as it plays back, blurring it
and distorting its colors in various ways while it rotates in space:
</p>
<pre>video {
  -webkit-filter: hue-rotate(0deg) saturate(1) blur(0);
  -webkit-transition: all 30s linear;
}
video.finished {
  -webkit-filter: hue-rotate(-180deg) saturate(10) blur(10px);
  -webkit-transform: translate(100px, 50px) rotateX(45deg) rotateY(-30deg) rotateZ(10deg);
}
</pre>
<p><a href="/wiki/File:videofade.png" class="image"><img alt="videofade.png" src="//static.webplatform.org/w/public/3/3d/videofade.png" width="962" height="495" /></a>
</p><p>Unlike <a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> functions,
<a href="/wiki/css/properties/filter" title="css/properties/filter"><b>filter</b></a> functions must be explictly
declared in each style sheet in the exact same order if they are to
transition.
</p><p><br />
</p><p><br />
</p>
<h2><span class="mw-headline" id="See_also">See also</span></h2>
<h3><span class="mw-headline" id="Related_articles">Related articles</span></h3>
<h4><span class="mw-headline" id="Transistions">Transistions</span></h4>
<ul><li> <a href="/wiki/CSS/Selectors/pseudo-classes/:target" title="CSS/Selectors/pseudo-classes/:target">:target pseudo-class selector</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/MediaStream/ended" title="apis/MediaStream/ended">Track ended</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/appcache" title="apis/appcache">appcache</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/appcache/ApplicationCache/status" title="apis/appcache/ApplicationCache/status">status</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/audio-video" title="apis/audio-video">audio-video</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/audio-video/AudioTrack/enabled" title="apis/audio-video/AudioTrack/enabled">enabled</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/audio-video/AudioTrack/language" title="apis/audio-video/AudioTrack/language">language</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/battery_status" title="apis/battery status">Battery Status API</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/canvas" title="apis/canvas">canvas</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions" title="apis/css-regions">CSS Regions API</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/CSSRegionStyleRule" title="apis/css-regions/CSSRegionStyleRule">CSSRegionStyleRule</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow" title="apis/css-regions/NamedFlow">NamedFlow</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow/firstEmptyRegionIndex" title="apis/css-regions/NamedFlow/firstEmptyRegionIndex">firstEmptyRegionIndex</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow/getContent" title="apis/css-regions/NamedFlow/getContent">getContent()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow/getRegions" title="apis/css-regions/NamedFlow/getRegions">getRegions()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow/getRegionsByContent" title="apis/css-regions/NamedFlow/getRegionsByContent">getRegionsByContent()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow/name" title="apis/css-regions/NamedFlow/name">name</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow/overset" title="apis/css-regions/NamedFlow/overset">overset</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow/regionfragmentchange" title="apis/css-regions/NamedFlow/regionfragmentchange">regionfragmentchange</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlow/regionoversetchange" title="apis/css-regions/NamedFlow/regionoversetchange">regionoversetchange</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlowCollection" title="apis/css-regions/NamedFlowCollection">NamedFlowCollection</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/NamedFlowCollection/namedItem" title="apis/css-regions/NamedFlowCollection/namedItem">namedItem()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/Region" title="apis/css-regions/Region">Region</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/Region/getComputedRegionStyle" title="apis/css-regions/Region/getComputedRegionStyle">getComputedRegionStyle()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/Region/getRegionFlowRanges" title="apis/css-regions/Region/getRegionFlowRanges">getRegionFlowRanges()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/css-regions/Region/regionOverset" title="apis/css-regions/Region/regionOverset">regionOverset</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/file" title="apis/file">file</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/filesystem" title="apis/filesystem">File System API</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/image_capture" title="apis/image capture">Mediastream Image Capture</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/image_capture/ImageCapture" title="apis/image capture/ImageCapture">ImageCapture</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/image_capture/PhotoSettings" title="apis/image capture/PhotoSettings">PhotoSettings</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/media_capture_and_streams" title="apis/media capture and streams">Media Capture and Streams</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/media_source_extensions/MediaSource" title="apis/media source extensions/MediaSource">MediaSource</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/media_source_extensions/MediaSource/appendBuffer" title="apis/media source extensions/MediaSource/appendBuffer">appendBuffer</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/media_source_extensions/VideoPlaybackQuality" title="apis/media source extensions/VideoPlaybackQuality">VideoPlaybackQuality</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/navigation_timing" title="apis/navigation timing">navigation timing</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/network_information" title="apis/network information">Network Information API</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/quota_management" title="apis/quota management">quota management</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/quota_management/StorageQuota" title="apis/quota management/StorageQuota">StorageQuota</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/quota_management/queryUsageAndQuota" title="apis/quota management/queryUsageAndQuota">queryUsageAndQuota</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/quota_management/requestQuota" title="apis/quota management/requestQuota">requestQuota</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/resource_timing" title="apis/resource timing">resource timing</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/user_timing" title="apis/user timing">user timing</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/vibration" title="apis/vibration">Vibration API</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/web_animations" title="apis/web animations">Web Animations API</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/web_animations/AnimationEffect/clone" title="apis/web animations/AnimationEffect/clone">clone</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/web_animations/AnimationNode" title="apis/web animations/AnimationNode">AnimationNode</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/web_animations/AnimationNode/timing" title="apis/web animations/AnimationNode/timing">timing</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/web_animations/AnimationPlayer/currentTime" title="apis/web animations/AnimationPlayer/currentTime">currentTime</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/apis/web_animations/AnimationPlayer/reverse" title="apis/web animations/AnimationPlayer/reverse">reverse</a></li></ul>
<pre><a href="/wiki/Special:Ask/-5B-5BTopic_Cluster::Transistions-5D-5D/-3FPage-20Title/format%3Dtemplate/link%3Dnone/template%3DSee_Also_Item/offset%3D50" title="Special:Ask/-5B-5BTopic Cluster::Transistions-5D-5D/-3FPage-20Title/format=template/link=none/template=See Also Item/offset=50">… further results</a><span class="smwttpersist" data-type="warning" data-context="persitent"><span class="smwtticon warning"></span><span class="smwttcontent">&quot;Transistions&quot; is not in the list of possible values (Canvas, CSS Font, CSS Layout, Animation, Audio, Background, Border, Box Model, CSS Attributes, CSSOM, Combinators, Deprecated, Document Structure, Exclusions, FileSystemAPI, Filters, Flexbox, Fonts, Generated and Replaced Content, Gradients, Grid Layout, HTML, Javascript, Multimedia, Media Queries, Mobile, Multi-Column, Off-line Storage, Paged Media, Performance, Pointer Events, Pseudo-Classes, Pseudo-Elements, Regions, Responsive Web Design, Ruby, Scrollbar, Selectors, Security, Shapes, SVG, Syntax, Tables, Text, Touch, Transforms, Transitions, Video, Visual Effects, Web Components, WebRTC, XHR) for this property.</span></span>
</pre>
<p><br />
</p>
<h3><span class="mw-headline" id="External_resources">External resources</span></h3>
<ul><li> <a rel="nofollow" class="external text" href="http://www.w3.org/TR/css3-transitions/">CSS Transitions: W3C Working Draft</a></li></ul>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>

<!-- Saved in parser cache with key wpwiki:pcache:idhash:7259-0!*!0!!*!5!*!esi=1 and timestamp 20150731181809 and revision id 23334
 -->
