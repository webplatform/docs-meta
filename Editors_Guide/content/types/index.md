---
title: Content types explained
summary: "As summarised on the WPD:Editors_Guide, we have three page types to enter standard documentation content into:\n"
tags:
  - Basic
  - Pages
todo_broken_links:
  note: 'During import MediaWiki could not find the following links, please fix and adjust this list.'
  links:
    - 'html lists'
    - 'html links'
    - 'creating basic lists'
    - 'implementing effective links'
    - 'building a horizontal navigation menu'
uri: 'Meta:Editors Guide/content/types'

---
## Summary

As summarised on the WPD:Editors\_Guide, we have three page types to enter standard documentation content into:

-   Reference material -- A concise description of an entity and its components; for example, JavaScript APIs, HTML and CSS reference.
-   Concepts -- Provides an overview of a feature or API.
-   Tutorials -- Step-by-step instructions for building a sample application or demonstrating a feature.

This document aims to describe in more detail the kind of content we should put in each type, and how the pages should work together for different subjects.

In all cases, you should whether a suitable page exists already before you start writing something, using the site's search functionality. If it does, all is not lost — you might well be able to improve what is already there.

Please note that when creating a new page, you should make all characters in the URL lower case.

## Reference material

The way reference documents work together is pretty simple. There are many different types of reference page available, as shown on [WPD:New\_Page](/WPD:New_Page); you just have to choose the correct one for the item you are documenting, be it a CSS property, or an API object property or method. You then have to fill in the correct location for the page to go — this should be self explanatory after reading the explanation below each page type.

when you have the right page type and location, you can't go far wrong — just fill in the different form fields within the form, and save it.

The reference pages don't need to be given much thought in terms of how they will play together; the site structure should make this work.

There is a good resource to help with creating new API pages, available at [WPD:Creating\_API\_pages](/WPD:Creating_API_pages).

## Concepts

A concept article should be created using the Concept page type. You should put it in a sensible place, as informed by [WPD:Content/Topic\_Hierarchy](/WPD:Content/Topic_Hierarchy). A concept article should provide an overview of whatever concept or technology you want to write about. What it's used for and/or entails, what the basic syntax is, gotcha and caveats, etc. If there are a lot of subtopics related to this one, you should create subpages

-   concepts/responsive web design/
-   concepts/responsive web design/introduction
-   concepts/responsive web design/breakpoints
-   concepts/responsive web design/responsive images
-   etc.

Concepts shouldn't contain step by step tutorial sections - these should be saved for tutorials!

## Tutorials

A tutorial article should contain step-by-step instructions for building some kind of app or feature, to demonstrate usage of a specific technology or technique. Tutorials should not contain all the high level purpose, background details and syntax that a concept article contains; it should just contain enough detail to allow the reader to work through the tutorial, along with further links to concept and reference articles for more details.

Tutorial articles should be created using the Tutorial page type, and put in a sensible place as informed by [WPD:Content/Topic\_Hierarchy](/WPD:Content/Topic_Hierarchy), for example

-   css/tutorials
-   css/tutorials/creating basic lists
-   css/tutorials/implementing a basic HTML image

## Tutorials working together with concepts

In many situations, a group of concept articles will exist on it's own, without tutorials, for example many of the articles at [concepts](/concepts) don't require accompanying tutorials. However, for more practical subjects such as [css](/css), a hybrid approach is needed, as you ought to explain the high level concepts in separate articles, and then have stand alone tutorials to teach their application. A tutorial might relate to more than one concept articles, and a concept article might point to a number of related tutorials, to learn about the different practical applications of those concepts.

For example

[html lists](/w/index.php?title=html_lists&action=edit&redlink=1) and [html links](/w/index.php?title=html_links&action=edit&redlink=1) are both good candidates for concept articles.

-   A good tutorial to follow on from [html lists](/w/index.php?title=html_lists&action=edit&redlink=1) might be [creating basic lists](/w/index.php?title=creating_basic_lists&action=edit&redlink=1), and could show how to build up a basic unordered, ordered, and description list.
-   A good tutorial to follow on from [html links](/w/index.php?title=html_links&action=edit&redlink=1) might be [implementing effective links](/w/index.php?title=implementing_effective_links&action=edit&redlink=1), and could show building a link with good link text, descriptive title, label to show what type of content is linked to, and maybe other best practices.
-   A good tutorial that would follow on from both the above concept article examples is [building a horizontal navigation menu](/w/index.php?title=building_a_horizontal_navigation_menu&action=edit&redlink=1), which will use lists and links.

In general, you should think of concept articles as being the core/nucleus articles, and the tutorials as being follow-ons from those concepts — this should inform the document hierarchy for different content domains. But different domains should definitely have a mix of tutorials and concepts where appropriate.

## Usage of exercise questions

A number of people are in favour of having exercise questions at the end of articles, as seen in [tutorials/using\_selectors](/tutorials/using_selectors). These originated in articles taken from the Opera web standards curriculum, so will not be found on many pages. But we should add some short test questions to as many concept and tutorial articles as we can.

These would be narrower in scope, and less involved that some of the in-depth tests/sample exam questions that we are planning to add as part of the educational resources that will be part of a later sub-project.

One question to answer is whether we should put these in the actual articles, or in separate pages? It would be nice to have them in page for ease of use, but there is also an argument for putting them in a separate page, as many of the questions will be quite similar between different articles.

We should definitely have inline questions in the proposed beginner's articles.

## Future plans

-   Make views available for readers to look at and work through just tutorials.
-   Update the naming/IA of the landing pages. The "Concepts" page should renamed to something like "General web concepts" or "Web theory". The tutorials pages should be renamed, as they are not just tutorials.
-   Assist Garbee in the creation of a new set of beginner's articles, to replace the current jumbled together set of links to regular HTML/CSS/JS tutorials and concepts. This needs to be a specially tailored set of articles for complete beginners.
-   Answer the question of where to put exercise questions.

