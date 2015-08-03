---
title: Meta:anim animations
---
<h1><span class="mw-headline" id="Making_things_move_with_CSS3_animations">Making things move with CSS3 animations</span></h1>
<p><b>By Mike Sierra</b><br />
</p>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>CSS animations allow you to build complex animated
sequences. Like <a href="/wiki/tutorials/css_transitions" title="tutorials/css transitions">transitions</a>, they
manipulate the CSS properties that control how interface elements
appear. Unlike transitions, they are not tied to shifts between style
sheets that distinguish interface states. Keyframe animations can
execute freely, and offer the best way to build complex effects into
an interface.
</p><p>To get the most from this tutorial, you should already be familiar
with <a href="/wiki/tutorials/css_transitions" title="tutorials/css transitions">CSS transitions</a>. Since they work
similarly, the term <i>CSS animations</i> often serves as a shorthand to
refer to transitions as well, but this tutorial only discusses
<i>keyframe animations</i>.
</p><p>These key points serve as reference:
</p>
<ul><li> The required <a href="/wiki/css/properties/animation-name" title="css/properties/animation-name"><b>animation-name</b></a> property specifies the name of a keyframe animation, and must correspond to a <a href="/wiki/css/atrules/@keyframes" title="css/atrules/@keyframes"><b>@keyframes</b></a> rule. Loading the CSS or applying a new name causes the animation to execute.</li></ul>
<ul><li> Use the required <a href="/wiki/css/properties/animation-duration" title="css/properties/animation-duration"><b>animation-duration</b></a> property to set the overall amount of time over which the animation executes, either in seconds or millseconds (<b>1s</b> == <b>1000ms</b>).</li></ul>
<ul><li> The <a href="/wiki/css/atrules/@keyframes" title="css/atrules/@keyframes"><b>@keyframes</b></a> rule declares the full sequence that corresponds to the <a href="/wiki/css/properties/animation-name" title="css/properties/animation-name"><b>animation-name</b></a>. Within the block, keyframes such as 0%, 50%, and 100% behave as selectors that manipulate CSS properties over the duration of the animation.</li></ul>
<ul><li> Any CSS property that be transitioned can also be animated.</li></ul>
<ul><li> Use <a href="/wiki/css/properties/animation-delay" title="css/properties/animation-delay"><b>animation-delay</b></a> to pause before executing an animation, using the same time values as for duration.</li></ul>
<ul><li> The <a href="/wiki/css/properties/animation-iteration-count" title="css/properties/animation-iteration-count"><b>animation-iteration-count</b></a> property sets the number of times the animation plays, either as an integer or <b>infinite</b>.</li></ul>
<ul><li> The <a href="/wiki/css/properties/animation-direction" title="css/properties/animation-direction"><b>animation-direction</b></a> property allows you to play the animation in <b>normal'<i> or </i>reverse</b> order, or <b>alternate</b> between the two for even/odd iterations.</li></ul>
<ul><li> The <a href="/wiki/css/properties/animation-fill-mode" title="css/properties/animation-fill-mode"><b>animation-fill-mode</b></a> property preserves an animation's start state before a delayed animation executes (<b>backwards</b>)), its end state after its final iteration (<b>forwards</b>), or <b>both</b>.</li></ul>
<ul><li> Set <a href="/wiki/css/properties/animation-play-state" title="css/properties/animation-play-state"><b>animation-play-state</b></a> to <b>pause</b> or <b>running</b> to stop and start animations.</li></ul>
<ul><li> The <a href="/wiki/css/properties/animation-timing-function" title="css/properties/animation-timing-function"><b>animation-timing-function</b></a> property controls the speed of progression between each keyframe, and can be altered within an animation. It uses the same set of keywords as transitions: <b>ease</b>, <b>ease-in</b>, <b>ease-out</b>, <b>ease-in-out</b>, <b>linear</b>, or custom <b>cubic-bezier()</b> functions.</li></ul>
<ul><li> The <a href="/wiki/css/properties/animation" title="css/properties/animation"><b>animation</b></a> shorthand property can represent values from all other animation properties. If two time measurements are included, they are interpreted first as duration then as delay.</li></ul>
<ul><li> Use standard property names along with <i>-webkit-</i> prefixes. Specify both the <b>@keyframes</b> rule and <b>@-webkit-keyframes</b>. From JavaScript, specify standard properties such as <b>animationName</b> along with <b>WebkitAnimationName</b>.</li></ul>
<ul><li> Use comma-separated property values to specify more than one animation. Animations that run concurrently cannot manipulate any of the same properties.</li></ul>
<ul><li> To modify <a href="/wiki/css/atrules/@keyframes" title="css/atrules/@keyframes"><b>@keyframes</b></a> rules dynamically, inject CSS into a local <b>style</b> region, or use the <a href="/wiki/css/cssom/CSSKeyframeRule" title="css/cssom/CSSKeyframeRule"><b>CSSKeyframeRule</b></a> interface.</li></ul>
<h2><span class="mw-headline" id="Animation_properties">Animation properties</span></h2>
<p>To understand how animations work, start with an example of a pulsing
icon, which may be used in a mobile interface to indicate what part of
an application is selected. The animation continuously shrinks and
grows one of the icons as it dims and brightens it. This simple
example will illustrate several other features below:
</p><p><a href="/wiki/File:anim_pulse.png" class="image"><img alt="anim pulse.png" src="//static.webplatform.org/w/public/6/64/anim_pulse.png" width="331" height="144" /></a>
</p><p>The <a href="/wiki/css/properties/animation" title="css/properties/animation"><b>animation</b></a> CSS property
specifies the <i>name</i> of an animation you will supply, <b>pulse</b> in
this case, and its overall <i>duration</i> of 1 second. Both are
required:
</p>
<pre>div.selected {
    animation&#160;: pulse 1s infinite;
}
</pre>
<p>The <b>infinite</b> keyword indicates that the animation repeats
indefinitely. If not specified, the animation executes only once.
</p><p>The <a href="/wiki/css/properties/animation" title="css/properties/animation"><b>animation</b></a> property is a
shorthand that combines the values of others:
</p>
<pre>div.selected {
    animation-name           &#160;: pulse;
    animation-duration       &#160;: 1s;
    animation-iteration-count&#160;: infinite;
}
</pre>
<p>Animation properties are standard in many browsers, but as of this
writing require prefixes for all WebKit browsers and older versions of
Gecko and Opera. For widest support, you should define animation
properties redundantly:
</p>
<pre>div.selected {
    -webkit-animation&#160;: pulse 1s infinite;
    -moz-animation   &#160;: pulse 1s infinite;
    -o-animation     &#160;: pulse 1s infinite;
    animation        &#160;: pulse 1s infinite;
}
</pre>
<p>From here on, examples feature only the un-prefixed property names.
</p>
<h2><span class="mw-headline" id="The_.40keyframes_rule">The @keyframes rule</span></h2>
<p>The <a href="/wiki/css/properties/animation-name" title="css/properties/animation-name"><b>animation-name</b></a> property
specifies an animation named <b>pulse</b>. Use a
<a href="/wiki/css/atrules/@keyframes" title="css/atrules/@keyframes"><b>@keyframes</b></a> rule within the CSS to
define each named animation sequence:
</p>
<pre>@keyframes pulse {
    from {
        transform&#160;: scale(1);
        opacity  &#160;: 1;
    }
    50% {
        transform&#160;: scale(0.75);
        opacity  &#160;: 0.25;
    }
    to {
        transform&#160;: scale(1);
        opacity  &#160;: 1;
    }
}
</pre>
<p>The entire sequence between <b>from</b> and <b>to</b> executes over the
span of time defined by the
<a href="/wiki/css/properties/animation-duration" title="css/properties/animation-duration"><b>animation-duration</b></a>
property. Each keyframe within the sequence behaves like a CSS
selector, manipulating the values of individual properties.
Shifts from one keyframe to another work the same as transitions,
and the same set of properties that can be transitioned can also be
manipulated in keyframes.
In this case, <a href="/wiki/css/properties/opacity" title="css/properties/opacity"><b>opacity</b></a> dims the icon
and <a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> shrinks it. (See the
<a href="/wiki/tutorials/css_transforms" title="tutorials/css transforms">tutorial on transforms</a> for details on the
<a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> property's <b>scale()</b>
function.)
</p><p>As with animation properties, each
<a href="/wiki/css/atrules/@keyframes" title="css/atrules/@keyframes"><b>@keyframes</b></a> rule also needs to be
prefixed redundantly to run on WebKit-based browsers such as Chrome
and Safari. The transform properties below are also prefixed:
</p>
<pre>@-webkit-keyframes pulse {
   0%   { -webkit-transform: scale(1)  &#160;; opacity: 1;    }
   50%  { -webkit-transform: scale(0.75); opacity: 0.25; }
   100% { -webkit-transform: scale(1)  &#160;; opacity: 1;    }
}
</pre>
<p>This example also substitutes <b>0%</b> and <b>100%</b> for their
synonymous keywords <b>from</b> and <b>to</b>. (If you don't specify
either, values transition from the next available keyframe in
the series.)
</p>
<h2><span class="mw-headline" id="Changing_Direction">Changing Direction</span></h2>
<p>This simple animation can also be alternated to produce the same effect:
</p>
<pre>div.selected {
    animation-name           &#160;: pulse;
    animation-duration       &#160;: 0.5s;
    animation-iteration-count&#160;: infinite;
    animation-direction      &#160;: alternate;
}
</pre>
<p>The <a href="/wiki/css/properties/animation-duration" title="css/properties/animation-duration"><b>animation-duration</b></a> is
now half of its previous value. Setting
<a href="/wiki/css/properties/animation-direction" title="css/properties/animation-direction"><b>animation-direction</b></a> to
<b>alternate</b> makes the animation execute in normal order
(<b>from</b>/<b>to</b>), then in reverse order (<b>to</b>/<b>from</b>) for
even-numbered iterations. This allows the animation's start and end
points to vary:
</p>
<pre>@keyframes pulse {
   from { transform: scale(1)  &#160;; opacity: 1;    }
   to   { transform: scale(0.75); opacity: 0.25; }
}
</pre>
<p>(You can also set
<a href="/wiki/css/properties/animation-direction" title="css/properties/animation-direction"><b>animation-direction</b></a> to
always <b>reverse</b>, or to <b>reverse-alternate</b>.)
</p>
<h2><span class="mw-headline" id="Multiple_animations">Multiple animations</span></h2>
<p>Animation properties accept more than one comma-delineated value,
which allows you to chain together different animations or run them
concurrently.
</p><p>This variation on the pulsing icon uses two keyframes to manipulate
the <a href="/wiki/css/properties/opacity" title="css/properties/opacity"><b>opacity</b></a> and
<a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> properties separately.
In this case, setting different durations makes the two <i>fade</i> and
<i>shrink</i> effects fall out of phase:
</p>
<pre>div.selected {
    animation: fade 0.5s infinite alternate, shrink 0.53s infinite alternate;
}
/* long form: */
div.selected {
    animation-name           &#160;: fade      , shrink   &#160;;
    animation-duration       &#160;: 0.5s      , 0.53s    &#160;;
    animation-iteration-count&#160;: infinite  , infinite &#160;;
    animation-direction      &#160;: alternate , alternate&#160;;
}
@keyframes fade {
    from { opacity  &#160;: 1; }
    to   { opacity  &#160;: 0.25; }
}
@keyframes shrink {
    from { transform&#160;: scale(1); }
    to   { transform&#160;: scale(0.75); }
}
</pre>
<p>Make sure that any keyframes or transitions that execute concurrently
don't manipulate any of the same properties. This is <i>not</i> a problem
for animations or transitions applied to different elements.
</p>
<h2><span class="mw-headline" id="Setting_a_Delay">Setting a Delay</span></h2>
<p>As with transitions, animations can be delayed before they execute.
Use the <a href="/wiki/css/properties/animation-delay" title="css/properties/animation-delay"><b>animation-delay</b></a>
property to wait some time before pulsing the icon:
</p>
<pre>div.selected {
    animation-name           &#160;: pulse;
    animation-duration       &#160;: 0.5s;
    animation-iteration-count&#160;: 6;
    animation-direction      &#160;: alternate;
    animation-delay          &#160;: 3s;
}
</pre>
<p>(In this version, the icon pulses three times.)
</p><p>Whenever two time measurements are specified in a shorthand property
value, the second is interpreted as the delay:
</p>
<pre>div.selected {
    animation&#160;: pulse 0.5s 3s infinite alternate;
}
</pre>
<p>This more elaborate example shows a delayed animation within a mobile
interface. After an initial pause, content shifts down to make room
for a series of banner advertisements, which then continuously cycle
horizontally and rewind to display the first:
</p><p><a href="/wiki/File:anim_cycle.png" class="image"><img alt="anim cycle.png" src="//static.webplatform.org/w/public/9/9b/anim_cycle.png" width="833" height="349" /></a>
</p><p>To achieve this effect, the
<a href="/wiki/css/properties/animation-delay" title="css/properties/animation-delay"><b>animation-delay</b></a> property
makes content shift down after 4 seconds. Here is the relevant CSS:
</p>
<pre>article {
    animation-name           &#160;: displaceContent;
    animation-duration       &#160;: 1s;
    animation-delay          &#160;: 4s;
    animation-iteration-count&#160;: 1;
    animation-fill-mode      &#160;: forwards;
}
@keyframes displaceContent {
    from { transform&#160;: translateY(0em) }
    to   { transform&#160;: translateY(3em) } /* slide down to make room for advertisements */
}
</pre>
<p>The
<a href="/wiki/css/properties/animation-iteration-count" title="css/properties/animation-iteration-count"><b>animation-iteration-count</b></a>
property makes the animation execute only once. (The next section
explains the
<a href="/wiki/css/properties/animation-fill-mode" title="css/properties/animation-fill-mode"><b>animation-fill-mode</b></a>
property.)
</p><p>The banner's first animation (<i>insertBanner</i>) closely mirrors that
of the content (<i>displaceContent</i>) shown above. After 4 seconds, it
slides into view from off the screen:
</p>
<pre>header {
    animation-name           &#160;: insertBanner , scrollBanner;
    animation-duration       &#160;: 1s           , 25s;
    animation-delay          &#160;: 4s           , 5s;
    animation-iteration-count&#160;: 1            , infinite;
    animation-fill-mode      &#160;: backwards    , none;
    width                    &#160;: 500%;        /* wide banner featuring 5 panels */
    column-count             &#160;: 5;
    column-gap               &#160;: 0;
}
@keyframes insertBanner {
    from { transform&#160;: translateY(-6em) } /* slide down from off-screen */
    to   { transform&#160;: translateY(0em) }
}
</pre>
<p>The banner's second animation (<i>scrollBanner</i>) takes over at the
5-second mark, after the first has completed. Over the course of 25
seconds, it shifts the banner sideways to view each advertisement for
nearly 5 seconds. After rewinding to its initial position 97% of the
way through the keyframes, setting
<a href="/wiki/css/properties/animation-iteration-count" title="css/properties/animation-iteration-count"><b>animation-iteration-count</b></a>
to <b>infinite</b> makes the animation replay indefinitely:
</p>
<pre>@keyframes scrollBanner {
    from { transform&#160;: translateX(0) }
    17%  { transform&#160;: translateX(0%) }
    20%  { transform&#160;: translateX(-20%) }
    37%  { transform&#160;: translateX(-20%) }
    40%  { transform&#160;: translateX(-40%) }
    57%  { transform&#160;: translateX(-40%) }
    60%  { transform&#160;: translateX(-60%) }
    77%  { transform&#160;: translateX(-60%) }
    80%  { transform&#160;: translateX(-80%) }
    97%  { transform&#160;: translateX(-80%) }
    to   { transform&#160;: translateX(0%) }
}
</pre>
<h2><span class="mw-headline" id="Fill_mode">Fill mode</span></h2>
<p>Each keyframe within an animation specifies CSS properties, just like
regular CSS selectors. Properties manipulated by keyframes may vary
from those defined or inherited by selectors. By default, after
animations complete their series of iterations, these properties
abruptly snap from the final keyframe's value back to their original
value. Likewise when animations are delayed, properties snap from
their original values to that of the first keyframe's value.
</p><p>The <a href="/wiki/css/properties/animation-fill-mode" title="css/properties/animation-fill-mode"><b>animation-fill-mode</b></a>
property fixes this problem. Setting it to <b>forwards</b> makes the
final keyframe's property values persist after the animation
completes. Setting it to <b>backwards</b> makes the first keyframe's
property override how the property would appear without the
animation. Setting it to <b>both</b> makes the keyframe's properties
override the element's default properties both before and after the
animation executes. Setting it to the default value of <b>none</b>
keeps all properties at their default values unless the animation is
executing.
</p><p>Note that none of these values make any difference for animations
whose <a href="/wiki/css/properties/animation-delay" title="css/properties/animation-delay"><b>animation-delay</b></a> is set
to zero, and whose
<a href="/wiki/css/properties/animation-iteration-count" title="css/properties/animation-iteration-count"><b>animation-iteration-count</b></a>
is <b>infinite</b>. Even then, they only make a difference for
properties whose values specified at the start or end of the animation
vary from how they are already specified by the element itself.
</p><p>The banner animation shown above gives an example of how to use
<a href="/wiki/css/properties/animation-fill-mode" title="css/properties/animation-fill-mode"><b>animation-fill-mode</b></a>.  By
default, both the banner and the main content inhabit the same space
at the top of the screen. The content's <i>displaceContent</i> animation
slides it out of its default position, and its fill-mode of
<b>forwards</b> keeps it there after it is done sliding. If it didn't,
it would snap right back to the top of screen. Likewise, the banner's
<i>insertBanner</i> animation slides it from a position specified in the
first keyframe, and its fill-mode of <b>backwards</b> keeps it there
before the delayed animation starts to execute, and it slides down to
its default position.
</p><p>Fill mode can override not only an element's underlying properties,
but other animations as well.  For the banner's second animation, the
<a href="/wiki/css/properties/animation-fill-mode" title="css/properties/animation-fill-mode"><b>animation-fill-mode</b></a> is
set to <b>none</b>. If it were set to <b>both</b> or <b>backwards</b>,
the first animation would not execute. Since animations are
interpreted in their order of declaration, and since both animations
manipulate the <a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> property,
specifying a fill-mode for the period before the second animation
executes would override whatever the first animation does with the
<b>transform</b> property:
</p>
<pre>header {
    /* both animations alter the 'transform' property: */
    animation-name           &#160;: insertBanner     , scrollBanner;
    /* animations execute in sequence: */
    animation-delay          &#160;: 4s               , 5s;
    animation-duration       &#160;: 1s               , 25s;
    animation-iteration-count&#160;: 1                , infinite;
    animation-fill-mode      &#160;: backwards        , none;
    /* 'none' does not clobber previous animation: ^^^^ */
}
</pre>
<h2><span class="mw-headline" id="Timing_functions">Timing functions</span></h2>
<p>The same set of timing functions that apply to transitions also apply
to animations. (For details on these functions, see
<a href="/wiki/tutorials/css_transitions#timing" title="tutorials/css transitions">Timing Functions</a>.)  The
<a href="/wiki/css/properties/animation-timing-function" title="css/properties/animation-timing-function"><b>animation-timing-function</b></a>
property allows you to control the response curve for each keyframe's
progress.  It recognizes keyword values <b>ease</b>, <b>ease-in</b>,
<b>ease-out</b>, <b>ease-in-out</b>, <b>linear</b>, along with
<b>cubic-bezier()</b> functions for custom response curves.
</p><p>By default, the <b>ease</b> value starts each keyframe slowly, builds
speed, then slows at the end, which is not always appropriate
behavior.  In this example, a series of items, skewed to appear
fast-moving, slide in haphazardly from the right edge of the screen,
then hit a wall at the left edge and wobble to a stop:
</p><p><a href="/wiki/File:animDelay.png" class="image"><img alt="animDelay.png" src="//static.webplatform.org/w/public/6/62/animDelay.png" width="546" height="367" /></a>
</p><p>Setting the timing function to <b>linear</b> makes the shift from a
moving to a stopped state as abrupt as possible. This occurs at the
70% keyframe:
</p>
<pre>div {
    animation-duration       &#160;: 0.5s;
    animation-fill-mode      &#160;: both;
    animation-iteration-count&#160;: 1;
    animation-name           &#160;: fastSlide;
    animation-timing-function&#160;: linear;
    transform-origin         &#160;: bottom;
}
@keyframes fastSlide {
    0%   { transform: translate(120%) skewX(-30deg)&#160;; }
    70%  { transform: translate(0%)   skewX(-30deg)&#160;; }
    80%  { transform: translate(0%)   skewX(20deg) &#160;; }
    95%  { transform: translate(0%)   skewX(-10deg)&#160;; }
    100% { transform: translate(0%)   skewX(0deg)  &#160;; }
}
</pre>
<p>For greater control, you can even manipulate the value of the
<a href="/wiki/css/properties/animation-timing-function" title="css/properties/animation-timing-function"><b>animation-timing-function</b></a>
property <i>within</i> each keyframe, so that it changes over the course
of the animation.
</p>
<h2><span class="mw-headline" id="Dynamic_animations">Dynamic animations</span></h2>
<p>The example above uses JavaScript to assign random delays to stagger
each animation's execution. Any animation property can be set directly
on an element's <b>style</b> object, but as of this writing you also
need to add alternative <i>Webkit</i>-prefixed property names:
</p>
<pre>window.onload = function() {
    var delay, divs = document.querySelectorAll('div');
    for (var i = 0, l = divs.length; i &amp;lt; l; i++) {
        // set delay up to 1 second:
        delay  = Math.round(Math.random() * 1000) + 'ms';
        divs[i].style.animationDelay = delay;
        divs[i].style.WebkitAnimationDelay = delay;
    }
}
</pre>
<p>Once an animation starts to execute, setting the
<a href="/wiki/css/properties/animation-play-state" title="css/properties/animation-play-state"><b>animation-play-state</b></a>
property to <b>pause</b> stops it, and a value of <b>running</b> resumes
it.
</p><p>To dynamically initiate an animation, specify a different name. In
this example, applying an <i>animate</i> class overrides the
<a href="/wiki/css/properties/animation-name" title="css/properties/animation-name"><b>animation-name</b></a> property's
default value, which is an empty string. The <i>sequence</i> animation
executes each time the class is applied after having been absent:
</p>
<pre>div         { -webkit-animation-name: "";       }
div.animate { -webkit-animation-name: sequence; }
</pre>
<p>Once the <i>animate</i> class is applied, simply reapplying it has no
effect, because the animation's name has to actualy change its
value. The same is true when applying the property directly to the
element. The first button below only works once, but the second can be
repeated because it responds to asynchronous mouse or touch input:
</p>
<pre>&amp;lt;div onclick="document.querySelector('#animation').style.WebkitAnimationName = 'sequence';"&gt;
REPLAY&amp;lt;/div&gt;

&amp;lt;div
   onmousedown='document.querySelector("#animation").style.WebkitAnimationName = "";'
   onmouseup='document.querySelector("#animation").style.WebkitAnimationName = "sequence";'
&gt;REPLAY&amp;lt;/div&gt;
</pre>
<p>As a workaround, you can inject CSS into a local <b>style</b> region.
Re-interpreting the CSS causes the animation to re-execute:
</p>
<pre>&amp;lt;style id="customCSS"&gt;&amp;lt;/style&gt;
. . .
&amp;lt;div onclick="replay()"&gt;REPLAY&amp;lt;/div&gt;
. . .
&amp;lt;script&gt;
function replay() {
    document.querySelector('#customCSS').textContent = 
        "div { animation-name: 'sequence'; -webkit-animation-name: 'sequence' }";
}
&amp;lt;/script&gt;
</pre>
<p>Applying a <a href="/wiki/css/atrules/@keyframes" title="css/atrules/@keyframes"><b>@keyframes</b></a> rule is a bit
more complex than it is to set properties. Perhaps the easiest way is
to inject the CSS into a <b>style</b> region in the same way as
described above:
</p>
<pre>var css = document.querySelector('#customCSS')
css.textContent += "@keyframes pulse { ";
css.textContent += "0% {transform:scale(1);opacity:1;} ";
css.textContent += "100% {transform:scale(0.75);opacity:0.25;} ";
css.textContent += "}";
</pre>
<p>A more formal API is available, especially to modify existing rules.
Briefly, suppose this is your first declared style:
</p>
<pre>@keyframes shiftColor {
   from { background-color: plum }
   to { background-color: #ddd }
}
</pre>
<p>Here is how you might change the initial color to a shade of gray:
</p>
<pre>var sources = document.styleSheets; // from link/style tags
var rules = sources[0].cssRules;    // list of all styles and at-rules
var rule = rules[0];                // get first
if( rule.type == rule.KEYFRAMES_RULE &amp;#124;&amp;#124; rule.type == rule.WEBKIT_KEYFRAMES_RULE ) {
    console.log(rule.name);         // shiftColor
    console.log(rule[0].cssText);   // 0% { background-color: rgb(221, 160, 221); }
    if ( rule[0].keyText == '0%' )  // 'from' converts to '0%'
        rule[0].style.backgroundColor = '#aaa';
    console.log(rule[0].cssText);   // 0% { background-color: rgb(170, 170, 170); }
}
</pre>
<p>See <a href="/wiki/css/cssom/CSSKeyframesRule" title="css/cssom/CSSKeyframesRule"><b>CSSKeyframesRule</b></a>, 
<a href="/wiki/css/cssom/CSSKeyframeRule" title="css/cssom/CSSKeyframeRule"><b>CSSKeyframeRule</b></a> and
<a href="/wiki/css/cssom/CSSRule" title="css/cssom/CSSRule"><b>CSSRule</b></a> for details.
</p><p><br />
</p><p><br />
</p>
<h2><span class="mw-headline" id="See_also">See also</span></h2>
<h3><span class="mw-headline" id="External_resources">External resources</span></h3>
<ul><li> <a rel="nofollow" class="external text" href="http://www.w3.org/TR/css3-animations/">CSS Animations: W3C Working Draft</a></li></ul>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>

<!-- 
NewPP limit report
CPU time usage: 0.167 seconds
Real time usage: 2.293 seconds
Preprocessor visited node count: 155/1000000
Preprocessor generated node count: 1408/1000000
Post‐expand include size: 22836/2097152 bytes
Template argument size: 23024/2097152 bytes
Highest expansion depth: 4/40
Expensive parser function count: 0/100
-->

<!-- 
Transclusion expansion time report (%,ms,calls,template)
100.00%   70.643      1 - -total
 18.35%   12.962      1 - Template:Flags
 16.60%   11.730      1 - Template:Page_Title
 11.50%    8.124      1 - Template:External_Attribution
 11.26%    7.953      1 - Template:Tutorial
  9.46%    6.684      1 - Template:Summary_Section
  8.24%    5.822      1 - Template:See_Also_Section
  5.84%    4.126      1 - Template:Notes_Section
  5.74%    4.056      1 - Template:Byline
  4.91%    3.471      1 - Template:Topics
-->

<!-- Saved in parser cache with key wpwiki:pcache:idhash:7261-0!*!0!!*!5!*!esi=1 and timestamp 20150730224005 and revision id 23341
 -->
