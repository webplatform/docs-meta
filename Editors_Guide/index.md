---
title: Meta:Editors Guide
---
<h1><span class="mw-headline" id="Editor.27s_Guide">Editor's Guide</span></h1>
<h2><span class="mw-headline" id="Overview">Overview</span></h2>
<p>This page is to centralize all the information an editor of WebPlatform Docs will need.
</p>
<h2><span class="mw-headline" id="What_to_know_in_advance">What to know in advance</span></h2>
<h3><span class="mw-headline" id="Style_guide">Style guide</span></h3>
<p>The <a href="/wiki/WPD:Manual_Of_Style" title="WPD:Manual Of Style" class="mw-redirect">style guide</a> for this site describes the conventions we have adopted for things like capitalization, title and section headings. Please be familiar with these conventions as you edit site content.
</p>
<h3><span class="mw-headline" id="Content_types">Content types</span></h3>
<p>WPD supports three basic types of content:
</p>
<ul><li> <b>Reference material</b> -- A concise description of an entity and its components; for example, JavaScript APIs, HTML and CSS reference. </li>
<li> <b>Tutorials</b> -- Step-by-step instructions for building a sample application or demonstrating a feature. </li>
<li> <b>Concepts</b> -- Provides an overview of a feature or API.</li></ul>
<p>Each of these content types has a unique URL name space--that is, where the page "lives". The URL generally follows the logical organization of the feature. For example, <a href="/wiki/css/selectors/outline-style" title="css/selectors/outline-style" class="mw-redirect">css/selectors/outline-style</a>.
</p>
<h2><span class="mw-headline" id="Editing_an_existing_page">Editing an existing page</span></h2>
<p>Editing an existing page is as easy as clicking the Edit button at the top of the page. Be sure you're familiar with the content types, architecture, and style guide before editing existing content or creating new content.
</p>
<h2><span class="mw-headline" id="Creating_a_new_page">Creating a new page</span></h2>
<p>Great, you have an idea for a new page you want to create, and you've determined the canonical URL where the content should live. For details on how to choose your page's URL, see <a href="/wiki/WPD:Architecture" title="WPD:Architecture">the architecture page</a>. The next step is to use the New Page form to create your page from the proper template, and at the proper URL.
</p><p><b>Steps for creating a new page</b>
</p>
<ol><li> Go to the <a href="/wiki/WPD:New_Page" title="WPD:New Page">New Page</a> page. </li>
<li> On that page identify the form to create the proper template (see <a href="#Choosing_a_content_template">#Choosing a content template</a>).</li>
<li> In the form's text field enter the URL for the new page in the text field, and click Create Page. </li></ol>
<p>For example, if you were creating a tutorial about a racing game, the URL might be <b>/tutorials/racing_game</b> (you would type in <b>tutorials/racing game</b>: the Wiki creates the underscores for you. Please do not use hyphens in urls unless grammatically appropriate, and use all lower case.).
</p>
<h3><span class="mw-headline" id="Architecture">Architecture</span></h3>
<p>For figuring out where to put new content, you'll need to get familiar with the <a href="/wiki/WPD:Content/Topic_Hierarchy" title="WPD:Content/Topic Hierarchy" class="mw-redirect">topic hierarchy</a> of this site.
</p>
<h3><span class="mw-headline" id="Choosing_a_content_template">Choosing a content template</span></h3>
<p>The <a href="/wiki/WPD:New_Page" title="WPD:New Page">New Page</a> page contains a form for each type of content you can create on the site. Each form consists of a text field where you enter the new page's URL and a button to create the page.
</p>
<ul><li> If you are creating a tutorial, use the <a href="/wiki/WPD:New_Page#Tutorial" title="WPD:New Page">Tutorial template</a>.</li>
<li> If you want to describe a concept or feature, use the <a href="/wiki/WPD:New_Page#Concept" title="WPD:New Page">Concept template</a>.</li>
<li> If you are creating a reference page, the template you select is determined by the kind of API/feature you are documenting, for example
<ul><li> <a href="/wiki/WPD:New_Page#API_Object_Method" title="WPD:New Page">API Object Method</a> for a method of an API/Object.</li>
<li> <a href="/wiki/WPD:New_Page#CSS_Property" title="WPD:New Page">CSS Property</a> for a CSS property.</li>
<li> etc.</li></ul></li></ul>
<p>The forms are listed in decreasing order of specificity. Identify the most specific form below that fits the type of content you'd like to create. For example
</p>
<h2><span class="mw-headline" id="The_basics">The basics</span></h2>
<h3><span class="mw-headline" id="The_technology">The technology</span></h3>
<p>WPD is a site dedicated to documenting and teaching people about open web standards, those technologies standardized by the W3C, IETF, and other standardization bodies, which are created as part of an open process to be free for anyone to use, and not controlled by any one company. If you think that a technology is missing from WPD, please open a discussion about it using any of the methods documented on our <a href="/wiki/WPD:Help" title="WPD:Help">Help page</a>.
</p>
<h3><span class="mw-headline" id="The_norms">The norms</span></h3>
<p>The WPD community is guided by a series of foundational norms that we call the <a href="/wiki/WPD:Pillars" title="WPD:Pillars" class="mw-redirect">WPD Pillars</a>. The Pillars document is a list of guiding principles that informs the more mundane norms and processes that govern the day-to-day operations of the site. You should read them carefully, but what's most important to know is that WPD is founded on the idea that we should assume good faith cooperation and that we prefer norms over rules. These norms and rules are documented within the wiki itself, in the WPD namespace (to keep it separate from documentation content). You can find the more mundane norms listed at <a href="/wiki/WPD:Policy" title="WPD:Policy">WPD:Policy</a>.
</p>
<h3><span class="mw-headline" id="Flags_and_editorial_notes">Flags and editorial notes</span></h3>
<p>WPD uses a system of flags and editorial notes to keep track of areas where improvements are required. when you choose to edit WPD pages, you should see a list of check boxes for the different flags available — use these to raise an alert that a specific type of improvement or attention is needed on a page.
</p>
<h3><span class="mw-headline" id="Compatibility_Tables">Compatibility Tables</span></h3>
<p>Web Platform Docs aims to have comprehensive, up-to-date compatibility information about most features. Sometimes some data may appear in multiple locations on the site. In order to ensure high data quality, it's important to follow these guidelines:
</p>
<ul><li> The canonical compatibility information should live on the most specific reference page about that feature. Often this is the page on the specific method, property, or css-property. It is <i>never</i> on a concept, tutorial, guide, or overview page.</li>
<li> You should import the canonical compatibility table on any page where it may be useful. For example, a tutorial on IndexedDB should import the canonical compatibility table from the relevant IndexedDB reference page. To do this, specify the Imported compatibility table field in the compatibility section of the page form to point at the page whose compatibility table you would like to import.</li></ul>
<p><br />
</p>
<h2><span class="mw-headline" id="References">References</span></h2>
<p>Here are some references to help you:
</p>
<ul><li> <a href="/wiki/WPD:Manual_Of_Style" title="WPD:Manual Of Style" class="mw-redirect">Style Guide</a></li>
<li> <a class="external text" href="http://www.mediawiki.org/wiki/Help:Formatting">MediaWiki Formatting</a></li>
<li> <a href="/wiki/WPD:Manual_Of_Style/Gotchas" title="WPD:Manual Of Style/Gotchas" class="mw-redirect">Wiki Syntax Errors (Gotchas)</a></li>
<li> <a href="/wiki/WPD:Implementation_Patterns" title="WPD:Implementation Patterns">How Web Platform Docs uses Semantic Media Wiki</a></li>
<li> <a href="/wiki/WPD:FAQ" title="WPD:FAQ">General FAQ</a></li>
<li> <a href="/wiki/WPD:Semantic_Forms" title="WPD:Semantic Forms">Semantic Forms</a></li></ul>
<p>Remember, if at any point you're unsure, ask the <a href="/wiki/WPD:Help" title="WPD:Help">IRC channel or the e-mail list</a>. We love helping new editors get the hang of things!
</p>
<h2><span class="mw-headline" id="Subpage_structure">Subpage structure</span></h2>
<p>Just an outline.  Will be removed once the guide is improved some more.
&lt;subpages /&gt;
</p>
<!-- 
NewPP limit report
CPU time usage: 0.035 seconds
Real time usage: 0.037 seconds
Preprocessor visited node count: 62/1000000
Preprocessor generated node count: 68/1000000
Post‐expand include size: 0/2097152 bytes
Template argument size: 0/2097152 bytes
Highest expansion depth: 2/40
Expensive parser function count: 0/100
-->

<!-- 
Transclusion expansion time report (%,ms,calls,template)
100.00%    0.000      1 - -total
-->

<!-- Saved in parser cache with key wpwiki:pcache:idhash:6306-0!*!0!!*!*!*!esi=1 and timestamp 20150731042644 and revision id 101021
 -->
