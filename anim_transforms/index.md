---
title: Meta:anim transforms
---
<h1><span class="mw-headline" id="Manipulating_content_with_CSS3_transforms">Manipulating content with CSS3 transforms</span></h1>
<p><b>By Mike Sierra</b><br />
</p>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>CSS transforms allow you to dynamically manipulate
the space in which content elements appear. You can move them around
on the screen, shrink or expand them, rotate them, or combine all
these effects to produce complex movements.  By themselves, transforms
produce static visual effects, but they can be easily combined with
CSS <a href="/wiki/tutorials/css_transitions" title="tutorials/css transitions">transitions</a> and
<a href="/wiki/tutorials/css_animations" title="tutorials/css animations">keyframe animations</a> to produce vibrant
animated interfaces. This tutorial first introduces simple
two-dimensional transforms, then shows you how to extend transforms
into three-dimensional space.  It ends with step-by-step instructions
to spin a cube in space.
</p><p>These key points serve as reference:
</p>
<ul><li> The <a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> property specifies a set of transform functions.</li></ul>
<ul><li> 2D functions include <a href="/wiki/css/functions/translate()" title="css/functions/translate()"><b>translate()</b></a>, <a href="/wiki/css/functions/scale()" title="css/functions/scale()"><b>scale()</b></a>, <a href="/wiki/css/functions/rotate()" title="css/functions/rotate()"><b>rotate()</b></a>, and <a href="/wiki/css/functions/skew()" title="css/functions/skew()"><b>skew()</b></a>.</li></ul>
<ul><li> The <a href="/wiki/css/functions/translate()" title="css/functions/translate()"><b>translate()</b></a> function accepts standard CSS measurements; <a href="/wiki/css/functions/scale()" title="css/functions/scale()"><b>scale()</b></a> accepts a decimal value between 0 and 1; both <a href="/wiki/css/functions/rotate()" title="css/functions/rotate()"><b>rotate()</b></a> and <a href="/wiki/css/functions/skew()" title="css/functions/skew()"><b>skew()</b></a> specify radial <b>deg</b> or <b>rad</b> measurements. Except for <a href="/wiki/css/functions/rotate()" title="css/functions/rotate()"><b>rotate()</b></a>, each accepts two <i>x</i>/<i>y</i> parameters.</li></ul>
<ul><li> Individual <i>x</i>/<i>y</i> functions are available: <a href="/wiki/css/functions/translateX()" title="css/functions/translateX()"><b>translateX()</b></a>, <a href="/wiki/css/functions/translateY()" title="css/functions/translateY()"><b>translateY()</b></a>, <a href="/wiki/css/functions/scaleX()" title="css/functions/scaleX()"><b>scaleX()</b></a>, <a href="/wiki/css/functions/scaleY()" title="css/functions/scaleY()"><b>scaleY()</b></a>, <a href="/wiki/css/functions/skewX()" title="css/functions/skewX()"><b>skewX()</b></a>, and <a href="/wiki/css/functions/skewY()" title="css/functions/skewY()"><b>skewY()</b></a></li></ul>
<ul><li> Combined 2D transforms can be represented with the <a href="/wiki/css/functions/matrix()" title="css/functions/matrix()"><b>matrix()</b></a> function, which uses 6 parameters.</li></ul>
<ul><li> 3D functions include <a href="/wiki/css/functions/rotateX()" title="css/functions/rotateX()"><b>rotateX()</b></a>, <a href="/wiki/css/functions/rotateY()" title="css/functions/rotateY()"><b>rotateY()</b></a>, <a href="/wiki/css/functions/rotate3d()" title="css/functions/rotate3d()"><b>rotate3d()</b></a>, <a href="/wiki/css/functions/translateZ()" title="css/functions/translateZ()"><b>translateZ()</b></a>, <a href="/wiki/css/functions/translate3d()" title="css/functions/translate3d()"><b>translate3d()</b></a>, <a href="/wiki/css/functions/scaleZ()" title="css/functions/scaleZ()"><b>scaleZ()</b></a>, and <a href="/wiki/css/functions/scale3d()" title="css/functions/scale3d()"><b>scale3d()</b></a>.</li></ul>
<ul><li> Combined 3D transforms can be represented with the <a href="/wiki/css/functions/matrix3d()" title="css/functions/matrix3d()" class="mw-redirect"><b>matrix3d()</b></a> function, which uses 16 parameters.</li></ul>
<ul><li> The <a href="/wiki/css/properties/transform-origin" title="css/properties/transform-origin"><b>transform-origin</b></a> property controls what point of an element the transform appears to emanate from. Adding a pixel measurement for a third parameter, or for the alternate <a href="/wiki/css/properties/transform-origin-z" title="css/properties/transform-origin-z"><b>transform-origin-z</b></a> property, moves the origin point back and forth in 3D space.</li></ul>
<ul><li> The <a href="/wiki/css/properties/perspective" title="css/properties/perspective"><b>perspective</b></a> property situates a 3D scene relative to the viewer, with distance measured in pixels. To appear correctly, it must be applied to a transformed element's ancestor.</li></ul>
<ul><li> The <a href="/wiki/css/properties/perspective-origin" title="css/properties/perspective-origin"><b>perspective-origin</b></a> property allows a 3D scene to be viewed from a diagonal vantage point rather than straight at the center.</li></ul>
<ul><li> The <a href="/wiki/css/properties/backface-visibility" title="css/properties/backface-visibility"><b>backface-visibility</b></a> property hides elements that rotate away from view, rather than rendering them as a mirror image.</li></ul>
<ul><li> Setting <a href="/wiki/css/properties/transform-style" title="css/properties/transform-style"><b>transform-style</b></a> to <b>preserve-3d</b> on a 3D element renders any nested 3D elements within its own transformed space.</li></ul>
<h2><span class="mw-headline" id="The_transform_property">The transform property</span></h2>
<p>Transforms alter a block element's coordinates in several ways so that
they vary from where they would ordinarily appear. The
<a href="/wiki/css/properties/transform" title="css/properties/transform"><b>transform</b></a> CSS property specifies a
handful of transformation <i>functions</i> that can be combined any way
you wish: <a href="/wiki/css/functions/translate()" title="css/functions/translate()"><b>translate()</b></a>,
<a href="/wiki/css/functions/scale()" title="css/functions/scale()"><b>scale()</b></a>,
<a href="/wiki/css/functions/rotate()" title="css/functions/rotate()"><b>rotate()</b></a>, and
<a href="/wiki/css/functions/skew()" title="css/functions/skew()"><b>skew()</b></a>.  Here is how you specify a
combination of most of the two-dimensional transforms discussed below,
along with a view of how the effect renders relative to the element's
default position:
</p>
<pre>div.card {
   -moz-transform   &#160;: translate(50%, 10%) rotate(20deg) scale(0.75);
   -o-transform     &#160;: translate(50%, 10%) rotate(20deg) scale(0.75);
   -webkit-transform&#160;: translate(50%, 10%) rotate(20deg) scale(0.75);
   transform        &#160;: translate(50%, 10%) rotate(20deg) scale(0.75);
}
</pre>
<p><a href="/wiki/File:transform_combo.png" class="image"><img alt="transform combo.png" src="//static.webplatform.org/w/public/4/4b/transform_combo.png" width="373" height="354" /></a>
</p><p>Transform properties were implemented recently enough that many
browsers only support them with <i>vendor prefixes</i> such as
<b>-moz-</b>, <b>-o-</b>, and <b>-webkit-</b> as shown above. Throughout
this tutorial, CSS examples only show the un-prefixed property name,
but for widest support you should apply all of them.
</p><p>Functions are separated by spaces, but any additional arguments are
separated by commas.
</p><p>While you can specify any number of these functions, values can't be
inherited from other style sheets. So you can't apply both of these
CSS classes to an element at the same time and expect both effects to
apply:
</p>
<pre>div.spin   { transform: rotate(20deg); }
div.tabled { transform: translate(100%) scale(0.5); }
</pre>
<p>Wherever you apply a transformation, any function left unspecified is
assigned a default value, so these work out the same as the less
verbose examples above:
</p>
<pre>div.spin { transform: rotate(20deg) translate(0,0), scale(1) skew(0,0) }
div.tabled { transform: rotate(0deg) translate(100%,0) scale(0.5) skew(0.0) }
</pre>
<p>You can also apply transforms directly to an object from JavaScript.
Here's an example in which tilting a mobile handset controls the tilt
of a screen element, using the 3D transforms described below:
</p>
<pre>var gestural = document.querySelector('#gestural');
window.addListener('deviceorientation', orientationHandler);
orientationHandler = function(e) {
   gestural.style.transform = 'rotateX(' + (e.beta * -1) + 'deg) ' + 'rotateY(' + e.gamma + 'deg)';
   gestural.style.WebkitTransform = 'rotateX(' + (e.beta * -1) + 'deg) ' + 'rotateY(' + e.gamma + 'deg)';
}
</pre>
<p>Several different technologies such as SVG and the <b>canvas</b>
element implement transforms, and are all conceptually similar despite
slight differences in how they are implemented.
</p>
<h2><span class="mw-headline" id="2D_transform_functions">2D transform functions</span></h2>
<p>The following isolates how each 2D function works. The
<a href="/wiki/css/functions/translate()" title="css/functions/translate()"><b>translate()</b></a> function simply moves
an element around on the screen, much the same as when using
<a href="/wiki/css/properties/top" title="css/properties/top"><b>top</b></a> and
<a href="/wiki/css/properties/left" title="css/properties/left"><b>left</b></a> to position an element. This
example moves the card over to the right more than it moves it
downward:
</p>
<pre>transform: translate(50%, 10%);
</pre>
<p><a href="/wiki/File:transform_translate.png" class="image"><img alt="transform translate.png" src="//static.webplatform.org/w/public/d/db/transform_translate.png" width="375" height="356" /></a>
</p><p>The <a href="/wiki/css/functions/translate()" title="css/functions/translate()"><b>translate()</b></a> function accepts
up to two <i>x</i> and <i>y</i> values to move to the right and
downward. These can specify any CSS measurement, including negative
values to move left and upward.  Percentages refer to the size of the
transformed element.  If you specify a single value, it's interpreted
as <i>x</i> and only moves the element horizontally.  Otherwise you can
specify separate <a href="/wiki/css/functions/translateX()" title="css/functions/translateX()"><b>translateX()</b></a> and
<a href="/wiki/css/functions/translateY()" title="css/functions/translateY()"><b>translateY()</b></a> functions. Here's
another way to express the same translation as above:
</p>
<pre>transform: translateX(50%) translateY(10%);
</pre>
<p>The <a href="/wiki/css/functions/scale()" title="css/functions/scale()"><b>scale()</b></a> function sizes an element
in decimal terms relative to a default value of 1. An element whose
scale is 2 doubles in size, while a scale of 0 vanishes into a point.
A single <b>scale</b> value applies to the whole element, but setting
two values lets you scale each axis independently, as you can also get
with separate <a href="/wiki/css/functions/scaleX()" title="css/functions/scaleX()"><b>scaleX()</b></a> and
<a href="/wiki/css/functions/scaleY()" title="css/functions/scaleY()"><b>scaleY()</b></a> functions.  The following
pairs offer different ways to produce the effects shown below:
</p>
<pre>/* first card */
transform: scale(0.75);
transform: scale(0.75, 0.75);
/* second card */
transform: scale(0.75, 1.25);
transform: scaleX(0.75) scaleY(1.25);
</pre>
<p><a href="/wiki/File:transform_scale.png" class="image"><img alt="transform scale.png" src="//static.webplatform.org/w/public/2/20/transform_scale.png" width="570" height="422" /></a>
</p><p>The <a href="/wiki/css/functions/rotate()" title="css/functions/rotate()"><b>rotate()</b></a> function spins an
element around its <i>z</i> axis.  It accepts a degree (<b>deg</b>) or
radian (<b>rad</b>) measurement. (Radians are equivalent to the number
of degrees multiplied by &#960;/180.) Radial measurements can wrap
around, so the following values are equivalent:
</p>
<pre>transform: rotate(20deg);
transform: rotate(380deg);  /*   360  + 20 */
transform: rotate(-340deg); /* (-360) + 20 */
</pre>
<p><a href="/wiki/File:transform_rotate.png" class="image"><img alt="transform rotate.png" src="//static.webplatform.org/w/public/7/79/transform_rotate.png" width="323" height="345" /></a>
</p><p>The <a href="/wiki/css/functions/skew()" title="css/functions/skew()"><b>skew()</b></a> function leans an element
over, altering its corner angle relative to the default 90&#176; and
transforming the underlying rectangle into a parallelogram.  It
accepts up to two degree (<b>deg</b>) or radian (<b>rad</b>)
measurements.  The separate <a href="/wiki/css/functions/skewX()" title="css/functions/skewX()"><b>skewX()</b></a>
function tips the side edges of the element, while
<a href="/wiki/css/functions/skewY()" title="css/functions/skewY()"><b>skewY()</b></a> tips the top and bottom.
Setting a single <a href="/wiki/css/functions/skew()" title="css/functions/skew()"><b>skew()</b></a> value affects
only the <i>x</i> axis.
</p>
<pre>transform: skewX(10deg);               /* 1st */
transform: skewY(-30deg);              /* 2nd */
transform: skew(10deg, -30deg);        /* 3rd */
transform: skewX(10deg) skewY(-30deg); /* 3rd, alternate syntax */
</pre>
<p><a href="/wiki/File:transform_skew.png" class="image"><img alt="transform skew.png" src="//static.webplatform.org/w/public/3/34/transform_skew.png" width="887" height="432" /></a>
</p><p>Note that skewing along both <i>x</i> and <i>y</i> makes the element appear to
move into three-dimensional space, but the transformation actually
occurs within a flat plane. Skip below for information about 3D
transforms.
</p><p><b>Note:</b> Browsers internally represent all of the transformations
described above as a single <i>matrix</i> expression, which for 2D
transforms consist of six values.  Using the web inspector feature,
you can view any transformed element's computed style for an example,
and use the the alternative <a href="/wiki/css/functions/matrix()" title="css/functions/matrix()"><b>matrix()</b></a>
function to specify those values.  Here is how the ace of spades in
the example above is represented as a matrix value:
</p>
<pre>transform: matrix(1, -0.577, 0.176, 1, 0, 0);
</pre>
<h2><span class="mw-headline" id="Changing_the_transform_origin">Changing the transform origin</span></h2>
<p>By default, transforms <i>originate</i> from the center of the element,
or 50% along both <i>x</i> and <i>y</i>.  If you scale it down, it shrinks
towards the center, or else you rotate it around its center point.
The <a href="/wiki/css/properties/transform-origin" title="css/properties/transform-origin"><b>transform-origin</b></a>
property allows you to place this origin point elsewhere, even outside
the element, changing how transforms respond, especially in animations.
It accepts a pair of <i>x</i>/<i>y</i> measurements.
</p><p>This shows a series of transforms that rotate around a point near the
bottom right corner:
</p>
<pre>div {
    transform-origin  &#160;: 80% 90%&#160;; 
}
div:nth-of-type(1) { transform&#160;: rotate(10deg)&#160;; }
div:nth-of-type(2) { transform&#160;: rotate(20deg)&#160;; }
div:nth-of-type(3) { transform&#160;: rotate(30deg)&#160;; }
</pre>
<p><a href="/wiki/File:origin_rotate.png" class="image"><img alt="origin rotate.png" src="//static.webplatform.org/w/public/1/16/origin_rotate.png" width="433" height="410" /></a>
</p><p>In this example, placing the origin of a skew transform at the bottom
makes it appear to tip over:
</p>
<pre>div {
   transform         &#160;: skewX(15deg);
   transform-origin  &#160;: bottom;
}
</pre>
<p><a href="/wiki/File:origin_skew.png" class="image"><img alt="origin skew.png" src="//static.webplatform.org/w/public/6/60/origin_skew.png" width="339" height="400" /></a>
</p><p>The property accepts the keywords <b>top</b> and <b>left</b> for
<b>0%</b>, <b>bottom</b> and <b>right</b> for <b>100%</b>, and
<b>center</b> for <b>50% 50%</b>.
</p><p>In the first of the following examples, placing the origin of a
<a href="/wiki/css/functions/scaleX()" title="css/functions/scaleX()"><b>scaleX()</b></a> transform along one edge
makes it appear to pivot along that edge. In the second, placing the
origin far outside the element's boundaries moves it across the screen
with no need for the <a href="/wiki/css/functions/translate()" title="css/functions/translate()"><b>translate()</b></a>
function:
</p>
<pre>div:first-of-type {
   transform       &#160;: scale(0.35, 1);
   transform-origin&#160;: 0%;
   transform-origin&#160;: left; /* same as 0% */
}
div:last-of-type {
   transform-origin&#160;: 210% -20%;
   transform       &#160;: scale(0.5);
}
</pre>
<p><a href="/wiki/File:origin_scale.png" class="image"><img alt="origin scale.png" src="//static.webplatform.org/w/public/0/0f/origin_scale.png" width="709" height="405" /></a>
</p>
<h2><span class="mw-headline" id="You_need_some_perspective">You need some perspective</span></h2>
<p>You really do.  Though they often take on the illusion of three
dimensions, 2D transforms are strictly superficial, inhabiting the
plane of the display screen. Three dimensional transforms allow
ordinary web content, which is still inherently flat, to shift onto
other planes.  But before applying the 3D transform functions
discussed below, you need to position the scene relative to the
viewer.
</p><p>Applying <i>perspective</i> to an an element indicates the viewer's
perceived distance to any transformed descendent elements.  The
<a href="/wiki/css/properties/perspective" title="css/properties/perspective"><b>perspective</b></a> property sets a
number of CSS pixels along the <i>z</i> axis that leads from the screen
to the viewer.  Since ordinary web content is inherently flat, all
measurements along the <i>z</i> axis <i>must</i> specify absolute units such
as pixels, rather than relative percentages that make sense along
<i>x</i> and <i>y</i>.
</p><p>The default <a href="/wiki/css/properties/perspective" title="css/properties/perspective"><b>perspective</b></a> value of
<b>none</b> indicates an infinite perspective, which appears flat.  A
value in the range of 1000 to 2000 mimics the distance at which people
typically view their screen.  Perspective values of less than 1000
appear increasingly distorted, but may be desirable for immersive
virtual reality applications in which the viewer appears to mingle
among displaying elements.
</p><p>The first scene in the example below shows a 3D rotation that appears
flat before applying <a href="/wiki/css/properties/perspective" title="css/properties/perspective"><b>perspective</b></a>,
while the second shows a distance of 1000.  The ancestor element's
<a href="/wiki/css/properties/border" title="css/properties/border"><b>border</b></a> reveals how the descendant's
plane has shifted.
</p>
<pre>.parent {
    border		: thin solid #000;
    perspective		: 1000;
    perspective-origin	: 50% 50%;
}
.child {
    transform		: rotateY(45deg);
}
</pre>
<p><a href="/wiki/File:transform_perspective.png" class="image"><img alt="transform perspective.png" src="//static.webplatform.org/w/public/f/fa/transform_perspective.png" width="799" height="405" /></a>
</p><p>While <a href="/wiki/css/properties/perspective" title="css/properties/perspective"><b>perspective</b></a> affects the
perceived distance to an object along the <i>z</i> axis, the
<a href="/wiki/css/properties/perspective-origin" title="css/properties/perspective-origin"><b>perspective-origin</b></a>
property allows you to shift the perceived location along <i>x</i> and
<i>y</i> from which it is viewed. The second scene reflects the default
<b>center</b> value in which the viewpoint is centered straight out
from the screen.  Altering these values positions the viewer
diagonally from the scene.  The third scene shows the same rotation,
but with the viewpoint shifted to the right:
</p>
<pre>perspective-origin-x&#160;: 500px;
</pre>
<p>This only affects how the transformed element appears, not the
ancestor that specifies the perspective.  Note that since percentages
refer to the size of the transformed element, pixel units may be
easier to use.
</p>
<h2><span class="mw-headline" id="3D_transforms">3D transforms</span></h2>
<p>To extend into three-dimensional space, enhanced functions allow
rotations around <i>x</i> and <i>y</i>, and translations into <i>z</i> space.
</p><p>The <a href="/wiki/css/functions/rotateX()" title="css/functions/rotateX()"><b>rotateX()</b></a> and
<a href="/wiki/css/functions/rotateY()" title="css/functions/rotateY()"><b>rotateY()</b></a> functions spin elements
around their horizontal or vertical axis, while the
<a href="/wiki/css/functions/rotateZ()" title="css/functions/rotateZ()"><b>rotateZ()</b></a> function behaves the same
as the 2D <a href="/wiki/css/functions/rotate()" title="css/functions/rotate()"><b>rotate()</b></a> function.
</p><p>An alternative <a href="/wiki/css/functions/rotate3d()" title="css/functions/rotate3d()"><b>rotate3d()</b></a> function
requires four arguments. The first three measurements specify a point
defining a 3D vector in <i>x</i>/<i>y</i>/<i>z</i> terms from the origin of the
element.  (For example, setting the vector to <b>-0.2,1,0.2</b> spins
the object as if it were a child's top leaning slightly forward and to
the left, while setting it to <b>0,1,0</b> would straighten it.)  The
fourth argument specifies the angle of rotation around that vector,
using <b>deg</b> or <b>rad</b> measurements.
</p><p>The <a href="/wiki/css/functions/translate3d()" title="css/functions/translate3d()"><b>translate3d()</b></a> function
requires three <i>x</i>, <i>y</i> and <i>z</i> measurements. Otherwise, use any
combination of <a href="/wiki/css/functions/translateX()" title="css/functions/translateX()"><b>translateX()</b></a>,
<a href="/wiki/css/functions/translateY()" title="css/functions/translateY()"><b>translateY()</b></a>, and
<a href="/wiki/css/functions/translateZ()" title="css/functions/translateZ()"><b>translateZ()</b></a> functions.  The
<i>z</i> translation must specify absolute measurements. The perceived
movement towards or away from the viewer depends on how much
perspective has been applied.
</p><p>The <a href="/wiki/css/functions/scale3d()" title="css/functions/scale3d()"><b>scale3d()</b></a> function accepts three
<i>x</i>, <i>y</i> and <i>z</i> measurements, otherwise they can be specified
separately with <a href="/wiki/css/functions/scaleX()" title="css/functions/scaleX()"><b>scaleX()</b></a>,
<a href="/wiki/css/functions/scaleY()" title="css/functions/scaleY()"><b>scaleY()</b></a>, and
<a href="/wiki/css/functions/scaleZ()" title="css/functions/scaleZ()"><b>scaleZ()</b></a>. Scaling along the <i>z</i>
axis ordinarily has no effect for flat web content, but does affect
the sort of nested 3D objects described in the next section.
</p><p>The <a href="/wiki/css/properties/transform-origin" title="css/properties/transform-origin"><b>transform-origin</b></a>
property accepts an additional third <b>z</b> measurement to place the
transformation point behind or in front of where the element displays,
in absolute units. (Alternately, specify the
<a href="/wiki/css/properties/transform-origin-z" title="css/properties/transform-origin-z"><b>transform-origin-z</b></a>
property.) This example shows a series of elements that rotate to
various degrees from an origin point within the gray parent box that
is far behind them:
</p><p><a href="/wiki/File:3d_originZ.png" class="image"><img alt="3d originZ.png" src="//static.webplatform.org/w/public/4/4a/3d_originZ.png" width="888" height="428" /></a>
</p>
<pre>.parent {
   perspective         &#160;: 10000;
   perspective-origin-y&#160;: -3000;  /* view from above */
   background-color    &#160;: #aaa;
}
.child {
   transform-origin-z  &#160;: -620;
   transform-origin    &#160;: 50% 50% -620;  /* same */
}
.child:nth-of-type(1) { transform: rotateY(-50deg); }
.child:nth-of-type(2) { transform: rotateY(-30deg); }
.child:nth-of-type(3) { transform: rotateY(-10deg); }
.child:nth-of-type(4) { transform: rotateY(10deg); }
.child:nth-of-type(5) { transform: rotateY(30deg); }
.child:nth-of-type(6) { transform: rotateY(50deg); }
</pre>
<p>By default, elements that rotate away from view display as a mirror
image. Changing the
<a href="/wiki/css/properties/backface-visibility" title="css/properties/backface-visibility"><b>backface-visibility</b></a>
property to <b>hidden</b> (from the default <b>visible</b>) enables
flip-panel effects in which elements only appear if they face the
viewer.
</p><p>This example shows a pair of child elements positioned at the same
coordinates within the parent <i>card</i>, but one of which is rotated to
face the other way. As described below, you can rotate the entire
card along with its children. In this case, with the backface hidden,
only one of the child <i>face</i> elements displays at a time:
</p>
<div dir="ltr" class="mw-geshi mw-code mw-content-ltr"><div class="xml source-xml"><pre class="de1"> <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;card&quot;</span><span class="re2">&gt;</span></span>
   <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;face&quot;</span> <span class="re0">id</span>=<span class="st0">&quot;jackheart&quot;</span><span class="re2">&gt;</span><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
   <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;face&quot;</span><span class="re2">&gt;</span><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
 <span class="sc3"><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span></pre></div></div>
<p><a href="/wiki/File:3d_backface.png" class="image"><img alt="3d backface.png" src="//static.webplatform.org/w/public/b/b0/3d_backface.png" width="948" height="301" /></a>
</p>
<pre>body {
    background		: #ddd;
    perspective		: 1200;
}
div {
    position		: absolute;
    width		: 280;
    height		: 400;
    border		: thin solid #777;
    border-radius	: 0.5em;
}
.card {
    left		: 0px;
    transform		: rotateY(45deg);    /* vary this to rotate the entire card */
    transform-style	: preserve-3d;    /* this allows each face to rotate within the card */
}
.face {
    background-size	: 100% 100%;
    backface-visibility	: hidden;    /* only display when facing viewer */
}
.face:first-of-type {
    transform		: rotateY(0deg);
}
.face:last-of-type {
    transform		: rotateY(180deg);
    background-image	: url(cardBack2.jpeg);
}
#jackheart {
    background-image	: url(JackHeart.jpeg);
}
</pre>
<p>While 2D transforms can be represented as a 6-element
<a href="/wiki/css/functions/matrix()" title="css/functions/matrix()"><b>matrix()</b></a> function, 3D transforms
correspond to 16-element <a href="/wiki/css/functions/matrix3d()" title="css/functions/matrix3d()" class="mw-redirect"><b>matrix3d()</b></a>
functions. Here's how an element might appear within the web
inspector's computed style panel:
</p>
<pre>transform: matrix3d(0.642, 0, 0.766, 0, 0, 1, 0, 0, -0.766, 0, 0.642, 0, 0, 0, 0, 1);
</pre>
<p><br />
</p>
<h2><span class="mw-headline" id="Nested_3D_transforms">Nested 3D transforms</span></h2>
<p>Applying a 3D rotation to an element aligns it to a different plane
than that of the viewing screen. Applying 3D translations and scale
effects also overrides the default coordinate system.  The
<a href="/wiki/css/properties/transform-style" title="css/properties/transform-style"><b>transform-style</b></a> property
allows you to transform nested content independently within that
already modified space.
</p><p>To clarify how to use this feature, this extended example builds a
cube representing playing dice that can spin freely. The markup
is implemented as a series of nested elements:
</p>
<div dir="ltr" class="mw-geshi mw-code mw-content-ltr"><div class="xml source-xml"><pre class="de1"> <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;scene&quot;</span><span class="re2">&gt;</span></span>
     <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;dice&quot;</span><span class="re2">&gt;</span></span>
         <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;centered&quot;</span><span class="re2">&gt;</span></span>
             <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;face&quot;</span><span class="re2">&gt;</span><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
             <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;face&quot;</span><span class="re2">&gt;</span><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
             <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;face&quot;</span><span class="re2">&gt;</span><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
             <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;face&quot;</span><span class="re2">&gt;</span><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
             <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;face&quot;</span><span class="re2">&gt;</span><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
             <span class="sc3"><span class="re1">&lt;div</span> <span class="re0">class</span>=<span class="st0">&quot;face&quot;</span><span class="re2">&gt;</span><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
         <span class="sc3"><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
     <span class="sc3"><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span>
 <span class="sc3"><span class="re1">&lt;/div<span class="re2">&gt;</span></span></span></pre></div></div>
<p>Global styles define absolutely positioned 100-pixel-square boxes. The
outlines will help clarify each nested transform:
</p>
<pre>div {
    box-sizing    &#160;: border-box;
    position      &#160;: absolute;
    width         &#160;: 100px;
    height        &#160;: 100px;
    outline-offset&#160;: 20px;
    outline-width &#160;: 3px;
    outline-style &#160;: solid;
}
</pre>
<p>The outermost <i>scene</i> element defines the overall perspective:
</p>
<pre>.scene {
    perspective  &#160;: 500;
    outline-color&#160;: pink;
}
</pre>
<p><a href="/wiki/File:3Dnest_scene.png" class="image"><img alt="3Dnest scene.png" src="//static.webplatform.org/w/public/8/80/3Dnest_scene.png" width="194" height="187" /></a>
</p><p>The next <i>dice</i> element is rotated arbitrarily:
</p>
<pre>.dice {
    transform      &#160;: rotateX(30deg) rotateY(50deg) rotateZ(20deg);
    transform-style&#160;: preserve-3d;
    outline-color  &#160;: lightgreen;
}
</pre>
<p><a href="/wiki/File:3Dnest_dice.png" class="image"><img alt="3Dnest dice.png" src="//static.webplatform.org/w/public/1/18/3Dnest_dice.png" width="218" height="223" /></a>
</p><p>The <b>preserve-3d</b> above renders any child element's transforms in
three dimensions relative to the <i>dice</i> element's own transformed
space. Otherwise the default <b>flat</b> value would make them appear
on the <i>dice</i> element's surface as if on a display screen.
</p><p>In this case, the nested <i>centered</i> element is there simply as a
convenience to drop the cube back to accomodate its full volume:
</p>
<pre>.centered {
    transform      &#160;: translateZ(-50px);
    transform-style&#160;: preserve-3d;
    outline-color  &#160;: gold;
}
</pre>
<p><a href="/wiki/File:3Dnest_centered.png" class="image"><img alt="3Dnest centered.png" src="//static.webplatform.org/w/public/e/ee/3Dnest_centered.png" width="218" height="230" /></a>
</p><p>Various properties define the dice's edges with rounded corners, along
with the small dot images that will be arranged to form a pattern on
each face. Only one dot displays in the first face's pattern, and the rest
are pushed outside the displaying area:
</p>
<pre>.face {
    border-radius      &#160;: 6px;
    border             &#160;: 2px solid #777;
    background-color   &#160;: #fff;
    background-repeat  &#160;: no-repeat;
    background-image   &#160;: url(dot.png), url(dot.png), url(dot.png),
                          url(dot.png), url(dot.png), url(dot.png);
    outline-color      &#160;: transparent;
}
.face:nth-of-type(1) {
    background-position&#160;: 40px 40px, -20px -20px, -20px -20px,
                         -20px -20px, -20px -20px, -20px -20px;
}

</pre>
<p><a href="/wiki/File:3Dnest_face1.png" class="image"><img alt="3Dnest face1.png" src="//static.webplatform.org/w/public/4/49/3Dnest_face1.png" width="237" height="235" /></a>
</p><p>The next four faces use 
<a href="/wiki/css/properties/transform-origin" title="css/properties/transform-origin"><b>transform-origin</b></a>
to pivot outward at right angles along each edge of the first face:
</p>
<pre>.face:nth-of-type(2) {
    transform          &#160;: rotateY(-90deg);
    transform-origin   &#160;: left;
    background-position&#160;: 10px 10px, -20px -20px, -20px -20px,
                         -20px -20px, -20px -20px, 70px 70px;
}
.face:nth-of-type(3) {
    transform          &#160;: rotateY(90deg);
    transform-origin   &#160;: right;
    background-position&#160;: 10px 10px, 40px 40px, -20px -20px,
                         -20px -20px, -20px -20px, 70px 70px;
}
.face:nth-of-type(4) {
    transform          &#160;: rotateX(90deg);
    transform-origin   &#160;: top;
    background-position&#160;: 10px 10px, -20px -20px, 10px 70px,
                          70px 10px, -20px -20px, 70px 70px;
}
.face:nth-of-type(5) {
    transform          &#160;: rotateX(-90deg);
    transform-origin   &#160;: bottom;
    background-position&#160;: 10px 10px, -20px -20px, 10px 70px,
                          70px 10px, 40px 40px, 70px 70px;
}

</pre>
<p><a href="/wiki/File:3Dnest_face5.png" class="image"><img alt="3Dnest face5.png" src="//static.webplatform.org/w/public/d/d9/3Dnest_face5.png" width="237" height="234" /></a>
</p><p>Note that all the backfaces are visible, and only become hidden when
other opaque boxes appear in front of them.
</p><p>The sixth face simply uses <b>translateZ()</b> to drop it back to close
off the cube:
</p>
<pre>.face:nth-of-type(6) {
    transform          &#160;: translateZ(-100px);
    transform-origin   &#160;: center;
    background-position&#160;: 10px 10px, 10px 40px, 10px 70px,
                          70px 10px, 70px 40px, 70px 70px;
}
</pre>
<p><a href="/wiki/File:3Dnest_face6.png" class="image"><img alt="3Dnest face6.png" src="//static.webplatform.org/w/public/b/b7/3Dnest_face6.png" width="211" height="226" /></a>
</p><p>Applying different rotations to the <i>dice</i> element causes nested
transform spaces to render relative to it, thus spinning the entire
object. Here is how a script can control the spin:
</p>
<pre>var diceStyle = document.querySelector('.dice').style;
diceStyle.transform = 'rotateX(' + spin() + ') ' + 'rotateY(' +
       spin() + ') ' + 'rotateZ(' + spin() + ') '&#160;;
// ...or diceStyle.WebkitTransform, diceStyle.MozTransform, etc.

function spin() { return( Math.floor( Math.random() * 360 ) + 'deg') }
</pre>
<p><a href="/wiki/File:3Dnest_spin.png" class="image"><img alt="3Dnest spin.png" src="//static.webplatform.org/w/public/2/2e/3Dnest_spin.png" width="680" height="457" /></a>
</p><p>Once such a complex 3D object takes up space, the effect of the
<a href="/wiki/css/functions/scaleZ()" title="css/functions/scaleZ()"><b>scaleZ()</b></a> or
<a href="/wiki/css/functions/scale3d()" title="css/functions/scale3d()"><b>scale3d()</b></a> functions becomes
apparent.  An animated transition between <b>scale3d(0,0,0)</b> and
<b>scale3d(1,1,1)</b> sizes the object in all three dimensions:
</p><p><a href="/wiki/File:scaleZ.png" class="image"><img alt="scaleZ.png" src="//static.webplatform.org/w/public/a/a1/scaleZ.png" width="582" height="219" /></a>
</p><p><br />
</p><p><br />
</p>
<h2><span class="mw-headline" id="See_also">See also</span></h2>
<h3><span class="mw-headline" id="Related_articles">Related articles</span></h3>
<h4><span class="mw-headline" id="Transforms">Transforms</span></h4>
<ul><li> <a href="/wiki/css/cssom/MSCSSMatrix/methods/inverse" title="css/cssom/MSCSSMatrix/methods/inverse">inverse</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/cssom/MSCSSMatrix/methods/multiply" title="css/cssom/MSCSSMatrix/methods/multiply">multiply</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/cssom/MSCSSMatrix/methods/rotate" title="css/cssom/MSCSSMatrix/methods/rotate">rotate</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/functions/rotate3d()" title="css/functions/rotate3d()">rotate3d()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/functions/scale3d()" title="css/functions/scale3d()">scale3d()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/functions/skew()" title="css/functions/skew()">skew()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/functions/translate()" title="css/functions/translate()">translate()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/functions/translate3d()" title="css/functions/translate3d()">translate3d()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/functions/translateX()" title="css/functions/translateX()">translateX()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/functions/translateY()" title="css/functions/translateY()">translateY()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/functions/translateZ()" title="css/functions/translateZ()">translateZ()</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/properties/backface-visibility" title="css/properties/backface-visibility">backface-visibility</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/properties/transform-origin-z" title="css/properties/transform-origin-z">transform-origin-z</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/transforms/MSCSSMatrix" title="css/transforms/MSCSSMatrix">MSCSSMatrix</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/css/transforms/MSCSSMatrix/translate" title="css/transforms/MSCSSMatrix/translate">translate</a></li></ul>
<p><br />
</p>
<ul><li> <a href="/wiki/tutorials/animation_in_javascript_2" title="tutorials/animation in javascript 2">JavaScript animation</a></li></ul>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>

<!-- 
NewPP limit report
CPU time usage: 0.449 seconds
Real time usage: 8.497 seconds
Preprocessor visited node count: 385/1000000
Preprocessor generated node count: 1889/1000000
Post‐expand include size: 30938/2097152 bytes
Template argument size: 26820/2097152 bytes
Highest expansion depth: 7/40
Expensive parser function count: 0/100
-->

<!-- 
Transclusion expansion time report (%,ms,calls,template)
100.00%  150.782      1 - -total
 43.06%   64.932      1 - Template:See_Also_Section
 12.30%   18.539      1 - Template:Page_Title
 11.68%   17.618     16 - Template:See_Also_Item
 10.07%   15.183      1 - Template:Flags
  9.73%   14.678      1 - Template:Tutorial
  6.04%    9.113      1 - Template:External_Attribution
  4.89%    7.369      1 - Template:Summary_Section
  3.35%    5.049      1 - Template:Byline
  3.23%    4.870      1 - Template:Notes_Section
-->

<!-- Saved in parser cache with key wpwiki:pcache:idhash:7260-0!*!0!!*!5!*!esi=1 and timestamp 20150731092929 and revision id 23337
 -->
