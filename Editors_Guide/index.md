=Editor's Guide=

==Overview==

This page is to centralize all the information an editor of WebPlatform Docs will need.

==What to know in advance==

===Style guide===

The [[WPD:Manual_Of_Style|style guide]] for this site describes the conventions we have adopted for things like capitalization, title and section headings. Please be familiar with these conventions as you edit site content.

===Content types===

WPD supports three basic types of content:

* '''Reference material''' -- A concise description of an entity and its components; for example, JavaScript APIs, HTML and CSS reference. 
* '''Tutorials''' -- Step-by-step instructions for building a sample application or demonstrating a feature. 
* '''Concepts''' -- Provides an overview of a feature or API.

Each of these content types has a unique URL name space--that is, where the page "lives". The URL generally follows the logical organization of the feature. For example, [[css/selectors/outline-style]].

==Editing an existing page==

Editing an existing page is as easy as clicking the Edit button at the top of the page. Be sure you're familiar with the content types, architecture, and style guide before editing existing content or creating new content.

== Creating a new page ==

Great, you have an idea for a new page you want to create, and you've determined the canonical URL where the content should live. For details on how to choose your page's URL, see [[WPD:Architecture|the architecture page]]. The next step is to use the New Page form to create your page from the proper template, and at the proper URL.

'''Steps for creating a new page'''

# Go to the [[WPD:New_Page|New Page]] page. 
# On that page identify the form to create the proper template (see [[#Choosing a content template]]).
# In the form's text field enter the URL for the new page in the text field, and click Create Page. 

For example, if you were creating a tutorial about a racing game, the URL might be '''/tutorials/racing_game''' (you would type in '''tutorials/racing game''': the Wiki creates the underscores for you. Please do not use hyphens in urls unless grammatically appropriate, and use all lower case.).

===Architecture===

For figuring out where to put new content, you'll need to get familiar with the [[WPD:Content/Topic_Hierarchy|topic hierarchy]] of this site.

=== Choosing a content template===

The [[WPD:New_Page|New Page]] page contains a form for each type of content you can create on the site. Each form consists of a text field where you enter the new page's URL and a button to create the page.

* If you are creating a tutorial, use the [[WPD:New_Page#Tutorial|Tutorial template]].
* If you want to describe a concept or feature, use the [[WPD:New_Page#Concept|Concept template]].
* If you are creating a reference page, the template you select is determined by the kind of API/feature you are documenting, for example
** [[WPD:New_Page#API_Object_Method|API Object Method]] for a method of an API/Object.
** [[WPD:New_Page#CSS_Property|CSS Property]] for a CSS property.
** etc.

The forms are listed in decreasing order of specificity. Identify the most specific form below that fits the type of content you'd like to create. For example

==The basics==
===The technology===

WPD is a site dedicated to documenting and teaching people about open web standards, those technologies standardized by the W3C, IETF, and other standardization bodies, which are created as part of an open process to be free for anyone to use, and not controlled by any one company. If you think that a technology is missing from WPD, please open a discussion about it using any of the methods documented on our [[WPD:Help|Help page]].

===The norms===
The WPD community is guided by a series of foundational norms that we call the [[WPD:Pillars|WPD Pillars]]. The Pillars document is a list of guiding principles that informs the more mundane norms and processes that govern the day-to-day operations of the site. You should read them carefully, but what's most important to know is that WPD is founded on the idea that we should assume good faith cooperation and that we prefer norms over rules. These norms and rules are documented within the wiki itself, in the WPD namespace (to keep it separate from documentation content). You can find the more mundane norms listed at [[WPD:Policy]].

===Flags and editorial notes===
WPD uses a system of flags and editorial notes to keep track of areas where improvements are required. when you choose to edit WPD pages, you should see a list of check boxes for the different flags available — use these to raise an alert that a specific type of improvement or attention is needed on a page.

===Compatibility Tables===
Web Platform Docs aims to have comprehensive, up-to-date compatibility information about most features. Sometimes some data may appear in multiple locations on the site. In order to ensure high data quality, it's important to follow these guidelines:
* The canonical compatibility information should live on the most specific reference page about that feature. Often this is the page on the specific method, property, or css-property. It is ''never'' on a concept, tutorial, guide, or overview page.
* You should import the canonical compatibility table on any page where it may be useful. For example, a tutorial on IndexedDB should import the canonical compatibility table from the relevant IndexedDB reference page. To do this, specify the Imported compatibility table field in the compatibility section of the page form to point at the page whose compatibility table you would like to import.


==References==

Here are some references to help you:

* [[WPD:Manual_Of_Style|Style Guide]]
* [http://www.mediawiki.org/wiki/Help:Formatting MediaWiki Formatting]
* [[WPD:Manual_Of_Style/Gotchas|Wiki Syntax Errors (Gotchas)]]
* [[WPD:Implementation_Patterns|How Web Platform Docs uses Semantic Media Wiki]]
* [[WPD:FAQ|General FAQ]]
* [[WPD:Semantic_Forms|Semantic Forms]]

Remember, if at any point you're unsure, ask the [[WPD:Help|IRC channel or the e-mail list]]. We love helping new editors get the hang of things!

==Subpage structure==
Just an outline.  Will be removed once the guide is improved some more.
<subpages />