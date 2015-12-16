---
title: 'Dynamic visual effects with CSS3 transitions'
notes:
  - 'import bug; real page is at css_transitions'
summary: "CSS transitions offer the easiest way to animate an\ninterface.  CSS is used everywhere to control how web pages appear,\nand shifts from one set of style sheets to another ordinarily occur\nabruptly.  Adding transition properties allows most of those changes\nto occur gradually, for a more vibrant, fluid interface.\n"
tags:
  - Tutorials
  - CSS
todo_broken_links:
  note: 'During import MediaWiki could not find the following links, please fix and adjust this list.'
  links:
    - 'before'''''''
    - 'after'''''''
    - selection
uri: 'Meta:Meta:tutorials anim transitions'

---
**By Mike Sierra**

## Summary

CSS transitions offer the easiest way to animate an interface. CSS is used everywhere to control how web pages appear, and shifts from one set of style sheets to another ordinarily occur abruptly. Adding transition properties allows most of those changes to occur gradually, for a more vibrant, fluid interface.

This tutorial introduces CSS's various transition properties and shows you how to control how smoothly transitions execute. It shows you how to create sequences of more than one transition, but increasingly complex movements require [keyframe animations](/tutorials/css_animations), which work similarly. You should become familiar with what CSS *transitions* can do before mastering *animations*. Both kinds of CSS-based animation require none of the JavaScript timers traditionally used to move things around, and they execute much faster.

While transitions allow you to apply hover effects and other relatively marginal enhancements to traditional desktop interfaces, they are particularly useful for small-screen mobile interfaces in which displaying elements need to slide or fade out of view, or else collapse into icons. Abrupt transitions can be particularly disorienting on a small screen.

These key points serve as reference:

-   Transitions are simple animations that smooth shifts from one style sheet to another.

-   Set [**transition-property**](/css/properties/transition-property) to specify which CSS property (or **all**) to animate between style sheets.

-   Properties that reference numeric measurements and color values can be transitioned.

-   The [**transition-duration**](/css/properties/transition-duration) property sets how much time the transition takes to run.

-   Use [**transition-delay**](/css/properties/transition-delay) to pause before executing a transition.

-   Use comma-delimited values to apply more than one transition to an element, useful in building sequences. Transitions can also execute concurrently when applied to different elements.

-   The [**transition-timing-function**](/css/properties/transition-timing-function) property allows you to control a transitions's speed of progress. It accepts keywords: **ease**, **ease-in**, **ease-out**, **ease-in-out**, **linear**, or custom **cubic-bezier()** response curves.

-   The [**transition**](/css/properties/transition) shorthand property can represent values from all other transition properties. If two time measurements are included, they are interpreted first as duration then as delay.

-   Specify a redundant set of property names prefixed *-webkit-*.

-   The **transitionend** event (or **webkitTransitionEnd**) fires at the end of a transition for each property that animates.

## The transition property

For transitions to work, there need to be two sets of style sheets that might apply to any element as users interact with the page. In this case, tapping a small **nav** element expands it out to a wider navigation panel:

![transit parent.png](//static.webplatform.org/f/f1/transit_parent.png)

To achieve this effect, a default style sheet defines most of how it appears. A second style sheet changes how it appears when it is assigned the *expanded* class.

    nav {
            /* transition applies to all varying elements */
        transition            : all 0.5s;
            /* dimensions and position (mostly outside view) */
        height                : 42px;
        width                 : 300px;
        position              : absolute;
        right                 : -260px;
        top                   : 10px;
        padding               : 2px;
        overflow              : hidden;
        box-sizing            : border-box;
            /* define icon */
        background-image      : url(html5.png);
        background-position-x : left;
        background-position-y : 50%;
        background-repeat     : no-repeat;
        background-size       : contain;
        background-color      : #fff;
            /* border and shadow hidden by default */
        border                : transparent solid medium;
        border-radius         : 4px;
        box-shadow            : 0 0 1em transparent;
    }
    nav.expanded  {
            /* transition applies to these varying elements */
        right                 : 10px;   /* bring panel into view */
        background-position-x : 400px;  /* icon out of view */
        border                : #aaa solid medium;
        box-shadow            : 0 0 1em #777;
    }

The *expanded* class specifies a handful of CSS properties that override those that apply without the class. Adding the [**transition**](/css/properties/transition) property makes those properties animate when toggling the class:

    -moz-transition    : all 0.5s;
    -o-transition      : all 0.5s;
    -webkit-transition : all 0.5s;
    transition         : all 0.5s;

Changes to the values of the [**right**](/css/properties/right) and [**background-position**](/css/properties/background-position) properties makes the element and its displaying icon slide in from the right. As it does, the border and shadow appear and get darker.

**Note:** Though transition properties were implemented recently enough, all browser engines but WebKit support them without *vendor* prefixes*such as **-moz-**, **-o-**, or **-webkit-** as shown* above. Still, you need prefixes to support older browser versions. Further examples only show un-prefixed transition property names, but for widest support you should apply all of them.

The [**transition**](/css/properties/transition) property specifies which properties to animate, **all** in this case, and the half second the animation takes to execute. It is shorthand for these separate properties:

    transition-property : all;
    transition-duration : 0.5s;
    transition-duration : 500ms; /* same as above, but expressed as milliseconds */

To see the animation in action, all you need is a mechanism to apply the *expanded* class, in this case a **click** handler that also responds to touch input:

    document.querySelector('nav').addEventListener('click', function(event) {
        event.currentTarget.classList.toggle('expanded');
    });

You'll notice that transitions respond very gracefully by reversing direction if you re-toggle the class while the animation is executing.

## Parallel transitions

We want the panel to display a set of nested navigation icons, in this case a set of horizontal **div** elements. A second [**transition**](/css/properties/transition) property animates these nested elements depending on the state of their parent **nav** element:

    nav > div {
        transition        : all 0.5s;
        height            : 34px;
        width             : 34px;
        background-size   : contain;
        display           : inline-block; /* arranged horizontally */
        opacity           : 0;            /* faded */
        transform         : scale(0);     /* scaled down */
    }
    nav.expanded > div {
        opacity           : 1;
        transform         : scale(1);
    }

The [**opacity**](/css/properties/opacity) property fades the icons, and [**transform**](/css/properties/transform) grows or shrinks them down to a point. (See the [tutorial on CSS transforms](/tutorials/css_transforms) for details.) Combined, the two sets of transitions execute simultaneously:

![transit simple.png](//static.webplatform.org/thumb/a/a3/transit_simple.png/280px-transit_simple.png)

For an element to be transitioned, it must specify a numeric value or percentage, such as a measurement or set of coordinates, or values that translate to numeric values, such as colors. Many keyword values work as well, such as the color **red** or **center** when used as a coordinate. But you cannot transition properties whose values specify a different kind of behavior. For example, you cannot transition between the [**display**](/css/properties/display) property's **block** and **none** values, or use [**text-align**](/css/properties/text-align) to switch between **left** and **right** justification.

**Note:** Generated content can be transitioned, but only by separately styling [before](/w/index.php?title=before%27%27%27&action=edit&redlink=1) and [after](/w/index.php?title=after%27%27%27&action=edit&redlink=1) selectors.

## Sequential transitions

You are not limited to a single set of transitions to get from one set of style sheets to another. The panel in this example first grows to its full width, then lengthens. The sequence is then reversed when collapsing the panel back down to icon size:

![transit sequence.png](//static.webplatform.org/thumb/b/bf/transit_sequence.png/900px-transit_sequence.png)

Here is the relevant CSS:

    div {
        width               : 56px;
        height              : 56px;
        transition-property : height , width;  /* collapse sequence */
        transition-duration : 0.5s   , 0.5s;
        transition-delay    : 0.0s   , 0.5s;   /* delay 2nd transition */
    }
    div.expanded {
        transition-property : width  , height; /* expand sequence */
        width               : 280px;
        height              : 400px;
    }

Each transition property uses commas to delimit additional transitions that form the larger second-long sequence. In this case, the duration for each is the same: half a second. The [**transition-delay**](/css/properties/transition-delay) property specifies that the first executes immediately, but the second waits until the first is complete.

This example also specifies individual property names rather than **all**. When transitioning to the *expanded* class, the [**width**](/css/properties/width) animates before the [**height**](/css/properties/height), and the sequence reverses in the other direction.

The [**transition**](/css/properties/transition) shorthand property also accommodates additional transitions. Here is the same as above, but expressed more tersely:

    div          { transition: height 0.5s 0.0s , width  0.5s 0.5s ; }
    div.expanded { transition: width  0.5s 0.0s , height 0.5s 0.5s ; }

The first supplied time value is interpreted as the [**transition-duration**](/css/properties/transition-duration), and the second as the [**transition-delay**](/css/properties/transition-delay).

Note that with no delay specified, you can use more than one transition to animate selected properties simultaneously, which might be useful if you want to animate some properties but not **all** of them. You can also stagger the delays so that execution overlaps. In this example, a single transition specifies the [**transform**](/css/properties/transform) property to move six cards to the right over the course of one second, but the delay for each is successively staggered up to half a second so that the overall sequence takes 1.5 seconds to execute:

    section > div {
        transition: transform 1s;
        transform: translateX(0px);
        /* ^^^ this transform is optional; transition assumes default value */
    }
    section.deal > div {
        transform: translateX(300px); /* move to right */
    }
    section > div:nth-of-type(6) {
        transition-delay: 0.0s;
        background-image: url(QueenSpade.png);
    }
    section > div:nth-of-type(5) {
        transition-delay: 0.1s;
        background-image: url(KingClub.jpeg);
    }
    section > div:nth-of-type(4) {
        transition-delay: 0.2s;
        background-image: url(JackClub.jpeg);
    }
    section > div:nth-of-type(3) {
        transition-delay: 0.3s;
        background-image: url(AceSpade.jpeg);
    }
    section > div:nth-of-type(2) {
        transition-delay: 0.4s;
        background-image: url(JackSpade.jpeg);
    }
    section > div:nth-of-type(1) {
        transition-delay: 0.5s;
        background-image: url(JackHeart.jpeg);
    }

The overall movement is staggered like this:

![transit delay.png](//static.webplatform.org/5/51/transit_delay.png)

<span id="timing"></span>

## Timing functions

You may notice in the example above that the cards are not evenly spaced. That's because transitions by default start out slowly, gather speed, then slow down again at the end. The [**transition-timing-function**](/css/properties/transition-timing-function) property specifies this behavior. By default it uses an **ease** value. If it were **linear**, they would all start and stop abruptly and move at the same speed:

![transit linear.png](//static.webplatform.org/9/95/transit_linear.png)

Browsers represent these keywords as bezier curves, which makes their response easier to visualize. Here is the basic set of keyword values along with their alternate **cubic-bezier()** functions. The animation's elapsed time and progress correspond to *x* and *y* axes, so the more the line curves vertically along the way, the faster the animation proceeds:

**linear**
**cubic-bezier(0.0, 0.0, 1.0, 1.0)** ![transitF linear.png](//static.webplatform.org/8/8e/transitF_linear.png)

**ease**
**cubic-bezier(0.25, 0.1, 0.25, 1.0)** ![transitF ease.png](//static.webplatform.org/7/73/transitF_ease.png)

**ease-in-out**
**cubic-bezier(0.42, 0, 0.58, 1.0)** ![transitF easeinout.png](//static.webplatform.org/6/67/transitF_easeinout.png)

**ease-in**
**cubic-bezier(0.42, 0, 1.0, 1.0)** ![transitF easein.png](//static.webplatform.org/6/64/transitF_easein.png)

**ease-out**
**cubic-bezier(0, 0, 0.58, 1.0)** ![transitF easeout.png](//static.webplatform.org/0/00/transitF_easeout.png)

This useful [cubic bezier function utility](http://cssglue.com/cubic) allows you to create your own custom curve and the see the result applied to various animations.

Timing functions can also be specified as part of the [**transition**](/css/properties/transition) shorthand property. This example makes a sequence of two **ease-in** and **ease-out** transitions resemble the behavior of a single **ease-in-out** function:

    div          { transition: height 0.5s 0.0s ease-in, width  0.5s 0.5s ease-out; }
    div.expanded { transition: width  0.5s 0.0s ease-in, height 0.5s 0.5s ease-out; }

As an alternative to response curves, the **steps()** function specifies a series of distinct frames with no smoothing applied. This animates three interim steps that occur between the start and end points:

    transition-timing-function : steps(5);

## The transitionend event

The **transitionend** event allows an application to respond after a transition finishes executing. The event fires on the element that is being transitioned, once for each property, and *only* if the specified transition actually modifies content.

In this example, applying a *display* class makes an information panel appear:

![transit end.png](//static.webplatform.org/1/13/transit_end.png)

The [**opacity**](/css/properties/opacity) property makes the element fade in, and is the only noticable change to its appearance. A second transition executes over a longer span of time, and makes an imperceptible change to the background color. Here is the relevant CSS:

    div {
        background-color : white;
        opacity          : 0;
        transition       : opacity 1s, background-color 5s;
    }
    div.display {
        opacity          : 1;
        background-color : rgba(100%, 100%, 100%, 0.95);
    }

After 5 seconds, a **transitionend** handler removes the *display* class to revert the element back to its original state:

    var panel = document.querySelector('.message');
    panel.addEventListener('transitionend'       , timeoutDisplay); // Standard: Gecko, IE10, Opera 12.10+
    panel.addEventListener('otransitionend'      , timeoutDisplay); // Old Opera
    panel.addEventListener('webkitTransitionEnd' , timeoutDisplay); // WebKit

    function timeoutDisplay(e) {
        // ignore irrelevant transitions:
        if (e.propertyName != 'background-color') return(false);
        // execute only after expanding panel:
        if (! e.currentTarget.classList.contains('display')) return(false);
        // collapse panel:
        e.currentTarget.classList.remove('display');
    }

Note the various provisional names for the event: **webkitTransitionEnd** (WebKit), **otransitionend** (old Opera), along with the standard **transitionend** (Gecko, Opera 12.10+, Internet Explorer).

<span id="advanced"></span>

## Advanced image transitions

While it's pretty obvious which properties can be transitioned, some browsers are adding support for a couple of unusual ones. So far these non-standard features can only be found in Webkit browsers.

Transitions between two [**background-image**](/css/properties/background-image) files now results in a cross-fade effect. Changing style sheets such as the following can thus drive an image gallery interface:

    div[data-img="4"] { background-image : url("Image04.jpg"); }
    div[data-img="5"] { background-image : url("Image05.jpg"); }

![fade.png](//static.webplatform.org/1/1e/fade.png)

See the [cross-fade()](/css/functions/cross-fade) function for a way to mix images statically.

**Note:** As of this writing, there is no support for transitions between [gradient](/css/functions/linear-gradient) background image values.

The [**filter**](/css/properties/filter) property allows you to apply sequences of image processing functions to any kind of visual element, and these effects can also be transitioned. This more unusual example applies a transition to a video as it plays back, blurring it and distorting its colors in various ways while it rotates in space:

    video {
      -webkit-filter: hue-rotate(0deg) saturate(1) blur(0);
      -webkit-transition: all 30s linear;
    }
    video.finished {
      -webkit-filter: hue-rotate(-180deg) saturate(10) blur(10px);
      -webkit-transform: translate(100px, 50px) rotateX(45deg) rotateY(-30deg) rotateZ(10deg);
    }

![videofade.png](//static.webplatform.org/3/3d/videofade.png)

Unlike [**transform**](/css/properties/transform) functions, [**filter**](/css/properties/filter) functions must be explictly declared in each style sheet in the exact same order if they are to transition.

## See also

### Related articles

#### Transistions

-   [:target pseudo-class selector](/CSS/Selectors/pseudo-classes/:target)

-   [Track ended](/apis/MediaStream/ended)

-   [appcache](/apis/appcache)

-   [status](/apis/appcache/ApplicationCache/status)

-   [audio-video](/apis/audio-video)

-   [enabled](/apis/audio-video/AudioTrack/enabled)

-   [language](/apis/audio-video/AudioTrack/language)

-   [Battery Status API](/apis/battery_status)

-   [canvas](/apis/canvas)

-   [CSS Regions API](/apis/css-regions)

-   [CSSRegionStyleRule](/apis/css-regions/CSSRegionStyleRule)

-   [NamedFlow](/apis/css-regions/NamedFlow)

-   [firstEmptyRegionIndex](/apis/css-regions/NamedFlow/firstEmptyRegionIndex)

-   [getContent()](/apis/css-regions/NamedFlow/getContent)

-   [getRegions()](/apis/css-regions/NamedFlow/getRegions)

-   [getRegionsByContent()](/apis/css-regions/NamedFlow/getRegionsByContent)

-   [name](/apis/css-regions/NamedFlow/name)

-   [overset](/apis/css-regions/NamedFlow/overset)

-   [regionfragmentchange](/apis/css-regions/NamedFlow/regionfragmentchange)

-   [regionoversetchange](/apis/css-regions/NamedFlow/regionoversetchange)

-   [NamedFlowCollection](/apis/css-regions/NamedFlowCollection)

-   [namedItem()](/apis/css-regions/NamedFlowCollection/namedItem)

-   [Region](/apis/css-regions/Region)

-   [getComputedRegionStyle()](/apis/css-regions/Region/getComputedRegionStyle)

-   [getRegionFlowRanges()](/apis/css-regions/Region/getRegionFlowRanges)

-   [regionOverset](/apis/css-regions/Region/regionOverset)

-   [file](/apis/file)

-   [File System API](/apis/filesystem)

-   [Mediastream Image Capture](/apis/image_capture)

-   [ImageCapture](/apis/image_capture/ImageCapture)

-   [PhotoSettings](/apis/image_capture/PhotoSettings)

-   [Media Capture and Streams](/apis/media_capture_and_streams)

-   [MediaSource](/apis/media_source_extensions/MediaSource)

-   [appendBuffer](/apis/media_source_extensions/MediaSource/appendBuffer)

-   [VideoPlaybackQuality](/apis/media_source_extensions/VideoPlaybackQuality)

-   [navigation timing](/apis/navigation_timing)

-   [Network Information API](/apis/network_information)

-   [quota management](/apis/quota_management)

-   [StorageQuota](/apis/quota_management/StorageQuota)

-   [queryUsageAndQuota](/apis/quota_management/queryUsageAndQuota)

-   [requestQuota](/apis/quota_management/requestQuota)

-   [resource timing](/apis/resource_timing)

-   [user timing](/apis/user_timing)

-   [Vibration API](/apis/vibration)

-   [Web Animations API](/apis/web_animations)

-   [clone](/apis/web_animations/AnimationEffect/clone)

-   [AnimationNode](/apis/web_animations/AnimationNode)

-   [timing](/apis/web_animations/AnimationNode/timing)

-   [currentTime](/apis/web_animations/AnimationPlayer/currentTime)

-   [reverse](/apis/web_animations/AnimationPlayer/reverse)

-   [source](/apis/web_animations/AnimationPlayer/source)

-   [AnimationPlayerEvent](/apis/web_animations/AnimationPlayerEvent)

-   [currentTime](/apis/web_animations/AnimationTimeline/currentTime)

-   [play](/apis/web_animations/AnimationTimeline/play)

-   [AnimationTimingReadOnly](/apis/web_animations/AnimationTimingReadOnly)

-   [localStorage](/apis/web-storage/Storage/localStorage)

-   [Web Audio API](/apis/webaudio)

-   [value](/apis/webaudio/AudioParam/value)

-   [WebRTC API](/apis/webrtc)

-   [XMLHttpRequest (XHR) API](/apis/xhr)

-   [XMLHttpRequest](/apis/xhr/XMLHttpRequest)

-   [WebRTC](/concepts/Internet_and_Web/webrtc)

-   [Pointer Events Primer](/concepts/Pointer_Events)

-   [Responsive Web Design](/concepts/mobile_web/responsive_design)

-   [Touch Input Considerations](/concepts/mobile_web/touch)

-   [@charset](/css/atrules/@charset)

-   [@font-face](/css/atrules/@font-face)

-   [@import](/css/atrules/@import)

-   [@keyframes](/css/atrules/@keyframes)

-   [@namespace](/css/atrules/@namespace)

-   [@page](/css/atrules/@page)

-   [@region](/css/atrules/@region)

-   [@supports](/css/atrules/@supports)

-   [color](/css/color)

-   [Colors by Hue](/css/color/colors_by_hue)

-   [Colors by Name](/css/color/colors_by_name)

-   [Colors by Saturation](/css/color/colors_by_saturation)

-   [User-Defined System Colors](/css/color/user-defined_system_colors)

-   [content fragments](/css/concepts/fragment)

-   [named flows](/css/concepts/named_flow)

-   [overset content](/css/concepts/overset)

-   [regions](/css/concepts/region)

-   [region chains](/css/concepts/region_chain)

-   [href](/css/cssom/CSSImportRule/href)

-   [media](/css/cssom/CSSImportRule/media)

-   [CSSKeyframeRule](/css/cssom/CSSKeyframeRule)

-   [keyText](/css/cssom/CSSKeyframeRule/keyText)

-   [style](/css/cssom/CSSKeyframeRule/style)

-   [CSSKeyframesRule](/css/cssom/CSSKeyframesRule)

-   [cssRules](/css/cssom/CSSKeyframesRule/cssRules)

-   [deleteRule](/css/cssom/CSSKeyframesRule/deleteRule)

-   [findRule](/css/cssom/CSSKeyframesRule/findRule)

-   [insertRule](/css/cssom/CSSKeyframesRule/insertRule)

-   [name](/css/cssom/CSSKeyframesRule/name)

-   [CSSMediaList](/css/cssom/CSSMediaList/CSSMediaList)

-   [appendMedium](/css/cssom/CSSMediaList/appendMedium)

-   [deleteMedium](/css/cssom/CSSMediaList/deleteMedium)

-   [item](/css/cssom/CSSMediaList/item)

-   [mediaText](/css/cssom/CSSMediaList/mediaText)

-   [CSSMediaRule](/css/cssom/CSSMediaRule/CSSMediaRule)

-   [cssRules](/css/cssom/CSSMediaRule/cssRules)

-   [deleteRule](/css/cssom/CSSMediaRule/deleteRule)

-   [insertRule](/css/cssom/CSSMediaRule/insertRule)

-   [media](/css/cssom/CSSMediaRule/media)

-   [CSSNamespaceRule](/css/cssom/CSSNamespaceRule/CSSNamespaceRule)

-   [namespaceURI](/css/cssom/CSSNamespaceRule/namespaceURI)

-   [prefix](/css/cssom/CSSNamespaceRule/prefix)

-   [CSSOM View](/css/cssom/CSSOM_view)

-   [CSSRule](/css/cssom/CSSRule)

-   [cssText](/css/cssom/CSSRule/cssText)

-   [parentRule](/css/cssom/CSSRule/parentRule)

-   [parentStyleSheet](/css/cssom/CSSRule/parentStyleSheet)

-   [type](/css/cssom/CSSRule/type)

-   [CSSStyleDeclaration](/css/cssom/CSSStyleDeclaration/CSSStyleDeclaration)

-   [getPropertyPriority](/css/cssom/CSSStyleDeclaration/getPropertyPriority)

-   [inverse](/css/cssom/MSCSSMatrix/methods/inverse)

-   [multiply](/css/cssom/MSCSSMatrix/methods/multiply)

-   [rotate](/css/cssom/MSCSSMatrix/methods/rotate)

-   [background](/css/cssom/properties/background)

-   [clipLeft](/css/cssom/properties/clipLeft)

-   [clipRight](/css/cssom/properties/clipRight)

-   [clipTop](/css/cssom/properties/clipTop)

-   [cssFloat](/css/cssom/properties/cssFloat)

-   [fontWeight](/css/cssom/properties/fontWeight)

-   [hasLayout](/css/cssom/properties/hasLayout)

-   [height](/css/cssom/properties/height)

-   [href](/css/cssom/properties/href)

-   [imports](/css/cssom/properties/imports)

-   [innerWidth](/css/cssom/properties/innerWidth)

-   [isAlternate](/css/cssom/properties/isAlternate)

-   [isPrefAlternate](/css/cssom/properties/isPrefAlternate)

-   [item](/css/cssom/properties/item)

-   [length](/css/cssom/properties/length)

-   [media](/css/cssom/properties/media)

-   [offsetX](/css/cssom/properties/offsetX)

-   [offsetY](/css/cssom/properties/offsetY)

-   [outerHeight](/css/cssom/properties/outerHeight)

-   [outerWidth](/css/cssom/properties/outerWidth)

-   [pageX](/css/cssom/properties/pageX)

-   [pageXOffset](/css/cssom/properties/pageXOffset)

-   [pageY](/css/cssom/properties/pageY)

-   [pageYOffset](/css/cssom/properties/pageYOffset)

-   [pixelBottom](/css/cssom/properties/pixelBottom)

-   [deviceXDPI](/css/cssom/screen/deviceXDPI)

-   [deviceYDPI](/css/cssom/screen/deviceYDPI)

-   [fontSmoothingEnabled](/css/cssom/screen/fontSmoothingEnabled)

-   [height](/css/cssom/screen/height)

-   [style](/css/cssom/style)

-   [type](/css/cssom/style/type)

-   [styleSheet](/css/cssom/styleSheet)

-   [addImport](/css/cssom/styleSheet/addImport)

-   [blockDirection](/css/cssom/styleSheet/blockDirection)

-   [cssRules](/css/cssom/styleSheet/cssRules)

-   [cssText](/css/cssom/styleSheet/cssText)

-   [ownerNode](/css/cssom/styleSheet/ownerNode)

-   [removeImport](/css/cssom/stylesheet/removeImport)

-   [removeRule](/css/cssom/stylesheet/removeRule)

-   [\<resolution\>](/css/data_types/resolution)

-   [ms-wrap-flow](/css/exclusions/ms-wrap-flow)

-   [ms-wrap-through](/css/exclusions/ms-wrap-through)

-   [Font related properties](/css/fonts)

-   [font-variant](/css/fonts/font-variant)

-   [blur()](/css/functions/blur)

-   [brightness()](/css/functions/brightness)

-   [contrast()](/css/functions/contrast)

-   [cubic-bezier](/css/functions/cubic-bezier)

-   [custom()](/css/functions/custom)

-   [drop-shadow()](/css/functions/drop-shadow)

-   [grayscale()](/css/functions/grayscale)

-   [hue-rotate()](/css/functions/hue-rotate)

-   [invert()](/css/functions/invert)

-   [linear-gradient](/css/functions/linear-gradient)

-   [opacity()](/css/functions/opacity)

-   [css/functions/radial-gradient](/css/functions/radial-gradient)

-   [repeating-linear-gradient](/css/functions/repeating-linear-gradient)

-   [repeating-radial-gradient](/css/functions/repeating-radial-gradient)

-   [rotate3d()](/css/functions/rotate3d())

-   [saturate()](/css/functions/saturate)

-   [scale3d()](/css/functions/scale3d())

-   [sepia()](/css/functions/sepia)

-   [skew()](/css/functions/skew())

-   [translate()](/css/functions/translate())

-   [translate3d()](/css/functions/translate3d())

-   [translateX()](/css/functions/translateX())

-   [translateY()](/css/functions/translateY())

-   [translateZ()](/css/functions/translateZ())

-   [Generated and Replaced Content](/css/generated_and_replaced_content)

-   [-ms-high-contrast](/css/high_contrast_mode/properties/-ms-high-contrast)

-   [ms-high-contrast-adjust](/css/high_contrast_modeapis/properties/ms-high-contrast-adjust)

-   [accelerator](/css/media_queries/accelerator)

-   [MediaQueryList](/css/media_queries/apis/MediaQueryList)

-   [MediaQueryListListener](/css/media_queries/apis/MediaQueryListListener)

-   [StyleMedia](/css/media_queries/apis/StyleMedia)

-   [addListener](/css/media_queries/apis/addListener)

-   [handleChange](/css/media_queries/apis/handleChange)

-   [matchMedia](/css/media_queries/apis/matchMedia)

-   [matchMedium](/css/media_queries/apis/matchMedium)

-   [matches](/css/media_queries/apis/matches)

-   [media](/css/media_queries/apis/media)

-   [type](/css/media_queries/apis/properties/type)

-   [removeListener](/css/media_queries/apis/removeListener)

-   [Colors by](/css/media_queries/colors_by)

-   [device-height](/css/media_queries/device-height)

-   [filter](/css/media_queries/filter)

-   [ms-interpolation-mode](/css/media_queries/ms-interpolation-mode)

-   [-ms-progress-appearance](/css/properties/-ms-progress-appearance)

-   [-ms-radial-gradient](/css/properties/-ms-radial-gradient)

-   [-ms-repeating-linear-gradient](/css/properties/-ms-repeating-linear-gradient)

-   [-ms-repeating-radial-gradient](/css/properties/-ms-repeating-radial-gradient)

-   [-ms-scrollbar-3d-light-color](/css/properties/-ms-scrollbar-3d-light-color)

-   [-ms-scrollbar-arrow-color](/css/properties/-ms-scrollbar-arrow-color)

-   [-ms-scrollbar-base-color](/css/properties/-ms-scrollbar-base-color)

-   [-ms-scrollbar-darkshadow-color](/css/properties/-ms-scrollbar-darkshadow-color)

-   [-ms-scrollbar-face-color](/css/properties/-ms-scrollbar-face-color)

-   [-ms-scrollbar-highlight-color](/css/properties/-ms-scrollbar-highlight-color)

-   [-ms-scrollbar-shadow-color](/css/properties/-ms-scrollbar-shadow-color)

-   [-ms-scrollbar-track-color](/css/properties/-ms-scrollbar-track-color)

-   [align-content](/css/properties/align-content)

-   [align-items](/css/properties/align-items)

-   [align-self](/css/properties/align-self)

-   [Animations](/css/properties/animations)

-   [backface-visibility](/css/properties/backface-visibility)

-   [background](/css/properties/background)

-   [background-attachment](/css/properties/background-attachment)

-   [background-blend-mode](/css/properties/background-blend-mode)

-   [background-clip](/css/properties/background-clip)

-   [background-color](/css/properties/background-color)

-   [background-image](/css/properties/background-image)

-   [background-origin](/css/properties/background-origin)

-   [background-position](/css/properties/background-position)

-   [background-position-x](/css/properties/background-position-x)

-   [background-position-y](/css/properties/background-position-y)

-   [background-repeat](/css/properties/background-repeat)

-   [background-size](/css/properties/background-size)

-   [behavior](/css/properties/behavior)

-   [block-progression](/css/properties/block-progression)

-   [border](/css/properties/border)

-   [border-bottom](/css/properties/border-bottom)

-   [border-bottom-color](/css/properties/border-bottom-color)

-   [border-bottom-left-radius](/css/properties/border-bottom-left-radius)

-   [border-bottom-style](/css/properties/border-bottom-style)

-   [border-bottom-width](/css/properties/border-bottom-width)

-   [border-collapse](/css/properties/border-collapse)

-   [border-color](/css/properties/border-color)

-   [border-corner-shape](/css/properties/border-corner-shape)

-   [border-image](/css/properties/border-image)

-   [border-image-outset](/css/properties/border-image-outset)

-   [border-image-repeat](/css/properties/border-image-repeat)

-   [border-image-slice](/css/properties/border-image-slice)

-   [border-image-source](/css/properties/border-image-source)

-   [border-image-width](/css/properties/border-image-width)

-   [border-left](/css/properties/border-left)

-   [border-left-color](/css/properties/border-left-color)

-   [border-left-style](/css/properties/border-left-style)

-   [border-left-width](/css/properties/border-left-width)

-   [border-radius](/css/properties/border-radius)

-   [border-right](/css/properties/border-right)

-   [border-right-color](/css/properties/border-right-color)

-   [border-right-style](/css/properties/border-right-style)

-   [border-right-width](/css/properties/border-right-width)

-   [border-spacing](/css/properties/border-spacing)

-   [border-top](/css/properties/border-top)

-   [border-top-color](/css/properties/border-top-color)

-   [border-top-left-radius](/css/properties/border-top-left-radius)

-   [border-top-right-radius](/css/properties/border-top-right-radius)

-   [border-top-style](/css/properties/border-top-style)

-   [border-top-width](/css/properties/border-top-width)

-   [border-width](/css/properties/border-width)

-   [bottom](/css/properties/bottom)

-   [box-decoration-break](/css/properties/box-decoration-break)

-   [box-flex](/css/properties/box-flex)

-   [box-lines](/css/properties/box-lines)

-   [box-ordinal-group](/css/properties/box-ordinal-group)

-   [box-orient](/css/properties/box-orient)

-   [box-pack](/css/properties/box-pack)

-   [box-shadow](/css/properties/box-shadow)

-   [box-sizing](/css/properties/box-sizing)

-   [break-after](/css/properties/break-after)

-   [break-before](/css/properties/break-before)

-   [break-inside](/css/properties/break-inside)

-   [caption-side](/css/properties/caption-side)

-   [clear](/css/properties/clear)

-   [clip](/css/properties/clip)

-   [column-count](/css/properties/column-count)

-   [column-gap](/css/properties/column-gap)

-   [column-rule](/css/properties/column-rule)

-   [column-rule-color](/css/properties/column-rule-color)

-   [column-rule-style](/css/properties/column-rule-style)

-   [column-rule-width](/css/properties/column-rule-width)

-   [column-span](/css/properties/column-span)

-   [column-width](/css/properties/column-width)

-   [content](/css/properties/content)

-   [counter-increment](/css/properties/counter-increment)

-   [counter-reset](/css/properties/counter-reset)

-   [cursor](/css/properties/cursor)

-   [empty-cells](/css/properties/empty-cells)

-   [filter](/css/properties/filter)

-   [flex](/css/properties/flex)

-   [flex-align](/css/properties/flex-align)

-   [flex-basis](/css/properties/flex-basis)

-   [flex-direction](/css/properties/flex-direction)

-   [flex-flow](/css/properties/flex-flow)

-   [flex-grow](/css/properties/flex-grow)

-   [flex-item-align](/css/properties/flex-item-align)

-   [flex-line-pack](/css/properties/flex-line-pack)

-   [flex-shrink](/css/properties/flex-shrink)

-   [flex-wrap](/css/properties/flex-wrap)

-   [float](/css/properties/float)

-   [flow-from](/css/properties/flow-from)

-   [flow-into](/css/properties/flow-into)

-   [font](/css/properties/font)

-   [font-family](/css/properties/font-family)

-   [font-feature-settings](/css/properties/font-feature-settings)

-   [font-kerning](/css/properties/font-kerning)

-   [font-language-override](/css/properties/font-language-override)

-   [font-size](/css/properties/font-size)

-   [font-size-adjust](/css/properties/font-size-adjust)

-   [font-stretch](/css/properties/font-stretch)

-   [font-style](/css/properties/font-style)

-   [font-synthesis](/css/properties/font-synthesis)

-   [font-variant](/css/properties/font-variant)

-   [grid-auto-rows](/css/properties/grid-auto-rows)

-   [grid-column-position](/css/properties/grid-column-position)

-   [grid-column-span](/css/properties/grid-column-span)

-   [grid-definition-columns](/css/properties/grid-definition-columns)

-   [grid-definition-rows](/css/properties/grid-definition-rows)

-   [grid-row-position](/css/properties/grid-row-position)

-   [hanging-punctuation](/css/properties/hanging-punctuation)

-   [height](/css/properties/height)

-   [hyphenate-limit-chars](/css/properties/hyphenate-limit-chars)

-   [hyphenate-limit-lines](/css/properties/hyphenate-limit-lines)

-   [hyphenate-limit-zone](/css/properties/hyphenate-limit-zone)

-   [hyphens](/css/properties/hyphens)

-   [ime-mode](/css/properties/ime-mode)

-   [justify-content](/css/properties/justify-content)

-   [kerning-mode](/css/properties/kerning-mode)

-   [kerning-pair-threshold](/css/properties/kerning-pair-threshold)

-   [layout-flow](/css/properties/layout-flow)

-   [layout-grid](/css/properties/layout-grid)

-   [layout-grid-char](/css/properties/layout-grid-char)

-   [layout-grid-line](/css/properties/layout-grid-line)

-   [layout-grid-mode](/css/properties/layout-grid-mode)

-   [layout-grid-type](/css/properties/layout-grid-type)

-   [left](/css/properties/left)

-   [letter-spacing](/css/properties/letter-spacing)

-   [line-break](/css/properties/line-break)

-   [line-height](/css/properties/line-height)

-   [list-style](/css/properties/list-style)

-   [list-style-image](/css/properties/list-style-image)

-   [list-style-position](/css/properties/list-style-position)

-   [list-style-type](/css/properties/list-style-type)

-   [margin](/css/properties/margin)

-   [margin-bottom](/css/properties/margin-bottom)

-   [margin-left](/css/properties/margin-left)

-   [margin-right](/css/properties/margin-right)

-   [margin-top](/css/properties/margin-top)

-   [max-font-size](/css/properties/max-font-size)

-   [max-height](/css/properties/max-height)

-   [max-width](/css/properties/max-width)

-   [min-font-size](/css/properties/min-font-size)

-   [min-height](/css/properties/min-height)

-   [min-width](/css/properties/min-width)

-   [object-fit](/css/properties/object-fit)

-   [opacity](/css/properties/opacity)

-   [text-overflow-ellipsis](/css/properties/text-overflow-ellipsis)

-   [text-overflow-mode](/css/properties/text-overflow-mode)

-   [text-rendering](/css/properties/text-rendering)

-   [text-underline](/css/properties/text-underline)

-   [text-underline-position](/css/properties/text-underline-position)

-   [text-underline-style](/css/properties/text-underline-style)

-   [text-underline-width](/css/properties/text-underline-width)

-   [transform-origin-z](/css/properties/transform-origin-z)

-   [transition](/css/properties/transition)

-   [transition-delay](/css/properties/transition-delay)

-   [transition-duration](/css/properties/transition-duration)

-   [transition-property](/css/properties/transition-property)

-   [user-input](/css/properties/user-input)

-   [user-modify](/css/properties/user-modify)

-   [user-select](/css/properties/user-select)

-   [widows](/css/properties/widows)

-   [zoom](/css/properties/zoom)

-   [CSS reference](/css/reference)

-   [Alphabetical list of CSS reference](/css/reference/alphabetical)

-   [Ruby](/css/ruby)

-   [querySelectorAll](/css/selectors_api/querySelectorAll)

-   [ID](/css/selectors/ID)

-   [Namespaced](/css/selectors/Namespaced)

-   [Universal](/css/selectors/Universal)

-   [equality](/css/selectors/attributes/equality)

-   [Attribute selector](/css/selectors/attributes/existence)

-   [hyphen](/css/selectors/attributes/hyphen)

-   [prefix](/css/selectors/attributes/prefix)

-   [substring](/css/selectors/attributes/substring)

-   [suffix](/css/selectors/attributes/suffix)

-   [whitespace](/css/selectors/attributes/whitespace)

-   [:-ms-input-placeholder](/css/selectors/pseudo-classes/:-ms-input-placeholder)

-   [:checked](/css/selectors/pseudo-classes/:checked)

-   [:disabled](/css/selectors/pseudo-classes/:disabled)

-   [:empty](/css/selectors/pseudo-classes/:empty)

-   [:enabled](/css/selectors/pseudo-classes/:enabled)

-   [:first-child](/css/selectors/pseudo-classes/:first-child)

-   [:first-of-type](/css/selectors/pseudo-classes/:first-of-type)

-   [:focus](/css/selectors/pseudo-classes/:focus)

-   [:in-range](/css/selectors/pseudo-classes/:in-range)

-   [:indeterminate](/css/selectors/pseudo-classes/:indeterminate)

-   [:invalid](/css/selectors/pseudo-classes/:invalid)

-   [:lang(c)](/css/selectors/pseudo-classes/:lang(c))

-   [:last-of-type](/css/selectors/pseudo-classes/:last-of-type)

-   [:nth-child(n)](/css/selectors/pseudo-classes/:nth-child(n))

-   [:nth-last-child(n)](/css/selectors/pseudo-classes/:nth-last-child(n))

-   [:nth-last-of-type(n)](/css/selectors/pseudo-classes/:nth-last-of-type(n))

-   [:nth-of-type(n)](/css/selectors/pseudo-classes/:nth-of-type(n))

-   [:only-child](/css/selectors/pseudo-classes/:only-child)

-   [:only-of-type](/css/selectors/pseudo-classes/:only-of-type)

-   [:optional](/css/selectors/pseudo-classes/:optional)

-   [:required](/css/selectors/pseudo-classes/:required)

-   [:root](/css/selectors/pseudo-classes/:root)

-   [:target](/css/selectors/pseudo-classes/:target)

-   [:valid](/css/selectors/pseudo-classes/:valid)

-   [::selection](/w/index.php?title=selection&action=edit&redlink=1)

-   [type](/css/selectors/type)

-   [!important](/css/syntax/!important)

-   [Tables](/css/tables)

-   [Text](/css/text)

-   [touch](/css/touch)

-   [MSCSSMatrix](/css/transforms/MSCSSMatrix)

-   [translate](/css/transforms/MSCSSMatrix/translate)

-   [hidden](/dom/Document/hidden)

-   [register](/dom/Document/register)

-   [visibilityState](/dom/Document/visibilityState)

-   [visibilitychange](/dom/Document/visibilitychange)

-   [releasePointerCapture](/dom/Element/releasePointerCapture)

-   [setPointerCapture](/dom/Element/setPointerCapture)

-   [FormData](/dom/FormData)

-   [HTMLAudioElement](/dom/HTMLAudioElement)

-   [textLength](/dom/HTMLTextAreaElement/textLength)

-   [value](/dom/HTMLTextAreaElement/value)

-   [MutationEvent](/dom/MutationEvent)

-   [attrChange](/dom/MutationEvent/attrChange)

-   [attrName](/dom/MutationEvent/attrName)

-   [initMutationEvent](/dom/MutationEvent/initMutationEvent)

-   [newValue](/dom/MutationEvent/newValue)

-   [prevValue](/dom/MutationEvent/prevValue)

-   [relatedNode](/dom/MutationEvent/relatedNode)

-   [maxTouchPoints](/dom/Navigator/maxTouchPoints)

-   [pointerEnabled](/dom/Navigator/pointerEnabled)

-   [PointerEvent](/dom/PointerEvent)

-   [propertyName](/dom/TransitionEvent/propertyName)

-   [getComputedStyle](/dom/Window/getComputedStyle)

-   [innerHeight](/dom/Window/innerHeight)

-   [styleMedia](/dom/Window/styleMedia)

-   [shadowdom](/dom/shadowdom)

-   [ShadowRoot](/dom/shadowdom/ShadowRoot)

-   [accept](/html/attributes/accept)

-   [action](/html/attributes/action)

-   [alt](/html/attributes/alt)

-   [autocomplete](/html/attributes/autocomplete)

-   [autofocus](/html/attributes/autofocus)

-   [capture](/html/attributes/capture)

-   [checked](/html/attributes/checked)

-   [crossorigin](/html/attributes/crossorigin)

-   [form](/html/attributes/form)

-   [formEnctype](/html/attributes/formEnctype)

-   [height](/html/attributes/height)

-   [is](/html/attributes/is)

-   [list](/html/attributes/list)

-   [max (HTMLInputElement)](/html/attributes/max_(HTMLInputElement))

-   [maxLength](/html/attributes/maxLength)

-   [min](/html/attributes/min)

-   [multiple](/html/attributes/multiple)

-   [readonly](/html/attributes/readonly)

-   [reset-style-inheritance](/html/attributes/reset-style-inheritance)

-   [size](/html/attributes/size)

-   [standby](/html/attributes/standby)

-   [step](/html/attributes/step)

-   [HTML Elements](/html/elements)

-   [!DOCTYPE](/html/elements/!DOCTYPE)

-   [!DOCTYPE](/html/elements/!DOCTYPE/ja)

-   [acronym](/html/elements/acronym)

-   [b](/html/elements/b)

-   [b](/html/elements/b/ja)

-   [bgSound](/html/elements/bgSound)

-   [bgsound](/html/elements/bgSound/ja)

-   [blink](/html/elements/blink)

-   [br](/html/elements/br)

-   [br](/html/elements/br/ja)

-   [button](/html/elements/button)

-   [button](/html/elements/button/ja)

-   [canvas](/html/elements/canvas)

-   [caption](/html/elements/caption)

-   [cite](/html/elements/cite)

-   [code](/html/elements/code)

-   [col](/html/elements/col)

-   [colgroup](/html/elements/colgroup)

-   [content](/html/elements/content)

-   [datalist](/html/elements/datalist)

-   [del](/html/elements/del)

-   [dfn](/html/elements/dfn)

-   [div](/html/elements/div)

-   [element](/html/elements/element)

<!-- -->

    … further results"Transistions" is not in the list of possible values (Canvas, CSS Font, CSS Layout, Animation, Audio, Background, Border, Box Model, CSS Attributes, CSSOM, Combinators, Deprecated, Document Structure, Exclusions, FileSystemAPI, Filters, Flexbox, Fonts, Generated and Replaced Content, Gradients, Grid Layout, HTML, Javascript, Multimedia, Media Queries, Mobile, Multi-Column, Off-line Storage, Paged Media, Performance, Pointer Events, Pseudo-Classes, Pseudo-Elements, Regions, Responsive Web Design, Ruby, Scrollbar, Selectors, Security, Shapes, SVG, Syntax, Tables, Text, Touch, Transforms, Transitions, Video, Visual Effects, Web Components, WebRTC, XHR) for this property.

### External resources

-   [CSS Transitions: W3C Working Draft](http://www.w3.org/TR/css3-transitions/)
