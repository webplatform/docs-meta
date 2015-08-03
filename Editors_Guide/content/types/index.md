---
title: Meta:Editors Guide/content/types
---
<h1><span class="mw-headline" id="Content_types_explained">Content types explained</span></h1>
<h2><span class="mw-headline" id="Summary">Summary</span></h2>
<p>As summarised on the <a href="/wiki/WPD:Editors_Guide" title="WPD:Editors Guide" class="mw-redirect">WPD:Editors_Guide</a>, we have three page types to enter standard documentation content into:
</p>
<ul><li> Reference material -- A concise description of an entity and its components; for example, JavaScript APIs, HTML and CSS reference.</li>
<li> Concepts -- Provides an overview of a feature or API. </li>
<li> Tutorials -- Step-by-step instructions for building a sample application or demonstrating a feature.</li></ul>
<p>This document aims to describe in more detail the kind of content we should put in each type, and how the pages should work together for different subjects.
</p><p>In all cases, you should whether a suitable page exists already before you start writing something, using the site's search functionality. If it does, all is not lost — you might well be able to improve what is already there.
</p><p>Please note that when creating a new page, you should make all characters in the URL lower case.
</p>
<h2><span class="mw-headline" id="Reference_material">Reference material</span></h2>
<p>The way reference documents work together is pretty simple. There are many different types of reference page available, as shown on <a href="/wiki/WPD:New_Page" title="WPD:New Page">WPD:New_Page</a>; you just have to choose the correct one for the item you are documenting, be it a CSS property, or an API object property or method. You then have to fill in the correct location for the page to go — this should be self explanatory after reading the explanation below each page type.
</p><p>when you have the right page type and location, you can't go far wrong — just fill in the different form fields within the form, and save it.
</p><p>The reference pages don't need to be given much thought in terms of how they will play together; the site structure should make this work.
</p><p>There is a good resource to help with creating new API pages, available at <a href="/wiki/WPD:Creating_API_pages" title="WPD:Creating API pages">WPD:Creating_API_pages</a>.
</p>
<h2><span class="mw-headline" id="Concepts">Concepts</span></h2>
<p>A concept article should be created using the Concept page type. You should put it in a sensible place, as informed by <a href="/wiki/WPD:Content/Topic_Hierarchy" title="WPD:Content/Topic Hierarchy" class="mw-redirect">WPD:Content/Topic_Hierarchy</a>. A concept article should provide an overview of whatever concept or technology you want to write about. What it's used for and/or entails, what the basic syntax is, gotcha and caveats, etc. If there are a lot of subtopics related to this one, you should create subpages
</p>
<ul><li> concepts/responsive web design/</li>
<li> concepts/responsive web design/introduction</li>
<li> concepts/responsive web design/breakpoints</li>
<li> concepts/responsive web design/responsive images</li>
<li> etc.</li></ul>
<p>Concepts shouldn't contain step by step tutorial sections - these should be saved for tutorials!
</p>
<h2><span class="mw-headline" id="Tutorials">Tutorials</span></h2>
<p>A tutorial article should contain step-by-step instructions for building some kind of app or feature, to demonstrate usage of a specific technology or technique. Tutorials should not contain all the high level purpose, background details and syntax that a concept article contains; it should just contain enough detail to allow the reader to work through the tutorial, along with further links to concept and reference articles for more details.
</p><p>Tutorial articles should be created using the Tutorial page type, and put in a sensible place as informed by <a href="/wiki/WPD:Content/Topic_Hierarchy" title="WPD:Content/Topic Hierarchy" class="mw-redirect">WPD:Content/Topic_Hierarchy</a>, for example
</p>
<ul><li> css/tutorials</li>
<li> css/tutorials/creating basic lists</li>
<li> css/tutorials/implementing a basic HTML image</li></ul>
<h2><span class="mw-headline" id="Tutorials_working_together_with_concepts">Tutorials working together with concepts</span></h2>
<p>In many situations, a group of concept articles will exist on it's own, without tutorials, for example many of the articles at <a href="/wiki/concepts" title="concepts">concepts</a> don't require accompanying tutorials. However, for more practical subjects such as <a href="/wiki/css" title="css">css</a>, a hybrid approach is needed, as you ought to explain the high level concepts in separate articles, and then have stand alone tutorials to teach their application. A tutorial might relate to more than one concept articles, and a concept article might point to a number of related tutorials, to learn about the different practical applications of those concepts.
</p><p>For example
</p><p><a href="/w/index.php?title=html_lists&amp;action=edit&amp;redlink=1" class="new" title="html lists (page does not exist)">html lists</a> and <a href="/w/index.php?title=html_links&amp;action=edit&amp;redlink=1" class="new" title="html links (page does not exist)">html links</a> are both good candidates for concept articles. 
</p>
<ul><li> A good tutorial to follow on from <a href="/w/index.php?title=html_lists&amp;action=edit&amp;redlink=1" class="new" title="html lists (page does not exist)">html lists</a> might be <a href="/w/index.php?title=creating_basic_lists&amp;action=edit&amp;redlink=1" class="new" title="creating basic lists (page does not exist)">creating basic lists</a>, and could show how to build up a basic unordered, ordered, and description list.</li>
<li> A good tutorial to follow on from <a href="/w/index.php?title=html_links&amp;action=edit&amp;redlink=1" class="new" title="html links (page does not exist)">html links</a> might be <a href="/w/index.php?title=implementing_effective_links&amp;action=edit&amp;redlink=1" class="new" title="implementing effective links (page does not exist)">implementing effective links</a>, and could show building a link with good link text, descriptive title, label to show what type of content is linked to, and maybe other best practices.</li>
<li> A good tutorial that would follow on from both the above concept article examples is <a href="/w/index.php?title=building_a_horizontal_navigation_menu&amp;action=edit&amp;redlink=1" class="new" title="building a horizontal navigation menu (page does not exist)">building a horizontal navigation menu</a>, which will use lists and links.</li></ul>
<p>In general, you should think of concept articles as being the core/nucleus articles, and the tutorials as being follow-ons from those concepts — this should inform the document hierarchy for different content domains. But different domains should definitely have a mix of tutorials and concepts where appropriate.
</p>
<h2><span class="mw-headline" id="Usage_of_exercise_questions">Usage of exercise questions</span></h2>
<p>A number of people are in favour of having exercise questions at the end of articles, as seen in <a href="/wiki/tutorials/using_selectors" title="tutorials/using selectors">tutorials/using_selectors</a>. These originated in articles taken from the Opera web standards curriculum, so will not be found on many pages. But we should add some short test questions to as many concept and tutorial articles as we can.
</p><p>These would be narrower in scope, and less involved that some of the in-depth tests/sample exam questions that we are planning to add as part of the educational resources that will be part of a later sub-project. 
</p><p>One question to answer is whether we should put these in the actual articles, or in separate pages? It would be nice to have them in page for ease of use, but there is also an argument for putting them in a separate page, as many of the questions will be quite similar between different articles.
</p><p>We should definitely have inline questions in the proposed beginner's articles.
</p><p><br />
</p>
<h2><span class="mw-headline" id="Future_plans">Future plans</span></h2>
<ul><li> Make views available for readers to look at and work through just tutorials.</li>
<li> Update the naming/IA of the landing pages. The "Concepts" page should renamed to something like "General web concepts" or "Web theory". The tutorials pages should be renamed, as they are not just tutorials.</li>
<li> Assist Garbee in the creation of a new set of beginner's articles, to replace the current jumbled together set of links to regular HTML/CSS/JS tutorials and concepts. This needs to be a specially tailored set of articles for complete beginners.</li>
<li> Answer the question of where to put exercise questions.</li></ul>
<p><br />
</p><p><br />
</p>
<div class="attribution">
<p><br />
</p><p><br />
</p>
</div>

<!-- 
NewPP limit report
CPU time usage: 0.086 seconds
Real time usage: 0.124 seconds
Preprocessor visited node count: 109/1000000
Preprocessor generated node count: 800/1000000
Post‐expand include size: 1319/2097152 bytes
Template argument size: 1776/2097152 bytes
Highest expansion depth: 4/40
Expensive parser function count: 0/100
-->

<!-- 
Transclusion expansion time report (%,ms,calls,template)
100.00%   48.811      1 - -total
 26.18%   12.778      1 - Template:Page_Title
 19.66%    9.594      1 - Template:Flags
 17.31%    8.448      1 - Template:External_Attribution
 11.95%    5.834      1 - Template:Summary_Section
  7.68%    3.748      1 - Template:Notes_Section
  6.42%    3.134      1 - Template:Basic_Page
  5.99%    2.922      1 - Template:Topics
-->

<!-- Saved in parser cache with key wpwiki:pcache:idhash:6655-0!*!0!!*!*!*!esi=1 and timestamp 20150730194753 and revision id 21495
 -->
