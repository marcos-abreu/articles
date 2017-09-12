# Communication through HTML

Historically developers tends to write ***HTML*** thinking on how things would look when rendered in the browser, instead of how the content that is been written should be structured in order to better convey the desired message.

This confusion has its roots on the history of web technologies and how they evolved over time. Long story short, for a very long time ***CSS*** capabilities were limited and therefore ***HTML***, for better or worse, stepped in to provide alternatives. 

Specifications such as `<b>` (bold), `<i>` (italics), `<u>` (underline), `<small>` (small font), `<big>` (big font), were originally created with presentation in mind not semantics.

In ***HTML4*** many presentational tags were deprecated, and in ***HMTL5*** those were removed (e.g: `<u>`, `<big>`) and the ones left (e.g: `<b>`, `<i>`, `<small>`) were given new semantic meaning.

***Semantic HTML*** refers to the idea that ***HTML*** markup should be used to convey the underlying meaning of your content and not its appearance.

## Why should we write Semantic HTML

When building the content of your pages, choosing the right words and sentences to convey your message is important, but it is only one part of the equation. Without a proper structure to support it, search engines, screen readers, and regular browsers, for the most part, just see the content as a bunch of meaningless data.

By improving semantic markup structure you create a higher quality content that can engage with visitors, attract others to your page, and allows everyone to proper consume your content, while at the same time getting more maintainable code.

In summary, you get maintainable code, delivering better usability, more searchable content, increase accessibility - all, if done properly, can lead to better conversion.

## Semantic HTML Tags

***Semantic HTML*** tags are tags that have a well defined role for both humans and machines. ***HTML*** has had semantic tags for a long time. Just think about `<form>` and `<img>` tags, they have a clear role that can be understood by both humans and machines.

In the past some of these ***Semantic Tags*** were abused for the lack of support for more meaningful ones (e.g: `<table>`), or the lack of understanding from us developers on how to use them (e.g: `<br>`). What lead to a community that had to sacrifice logical structure for visual layout.

The ***HTML*** specification and browser implementation has come a long way, with better support for semantic content, either by eliminating most (not all) presentational tags that can be better supported by ***CSS*** rules, or by adding new semantic tags, and better defining the meaning of existing ones.

In addition, the current open discussion format about new features being introduced to the language since its draft days, has lead to a variety of material that can help developers better understand and prepare when time comes to properly use them.

## Section Elements

***HTML*** specifies a set of elements designed to add meaning to the overall layout of your document and its parts, these elements are called ***section elements***.

`<body>` - represent the content of an ***HTML*** document. Only one per document.

`<nav>` - collection of internal or external navigation links.

`<aside>` - complementary content tangible to the content surrounding it.

`<article>` - self-contained content that can be distributed outside of the context of the page.

`<section>` - a group of related content around a specific theme.

Use these semantic elements instead of generic `<div>` elements to provide a more concrete meaning to the parts of your document.

---
The rule of thumb when you need a sectioning content element is:

1. check if it matches the definition of `<nav>`, if so go with it, otherwise:
1. check if it matches the definition of `<aside>`, if so go with it, otherwise:
1. check if it matches the definition of `<article>`, if so go with it, otherwise:
1. it is most likely a `<section>`
---

There is also a `<main>` block used to represent the main content of a section, most likely the `<body>` section. Only one per document as implemented by browsers, but contrary from [**WHATWG** living standard](https://html.spec.whatwg.org/multipage/grouping-content.html#the-main-element) defines.

The `<header>` (header of a document or a section) and `<footer>` (footer of a document or a section) tags are also used to divide up the content, but they don't generate sections in a document. So every `<body>`, `<article>`, `<section>`, `<nav>` and `<aside>` can have their own `<header>` and `<footer>`.

## Document Outline

Every ***HTML*** page has an outline, which is how search engines and most screen readers understand the hierarchy of your page. The notion of section and sub-sections and their relationship is what forms the **document outline**.

Even with the new section elements, as of today the specs still recommend the use of heading tags (`<h1>...<h6>`), where their rank should match with the section levels to provide an appropriate **document outline**. You can check some of the reasons [here](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines) and see the specs [here](https://html.spec.whatwg.org/multipage/sections.html#headings-and-sections) and [here](https://html.spec.whatwg.org/multipage/sections.html#the-h1,-h2,-h3,-h4,-h5,-and-h6-elements).

## Content Elements

As seen you have many tags to help you better structure your pages, but ***HTML*** have more tags that helps you better describe your content, bellow are some of the most common tags of this category:

`<address>` - represent the contact information of a page, or site

`<strong>` - gives the text strong emphasis

`<em>` - gives the text emphasis

`<time>` - 

`<blockquote>` - 

`<cite>` - 

`<code>` - 

`<figure>` -

`<mark>` - highlight reference text, due to its importance in another context.

https://www.thoughtco.com/why-use-semantic-html-3468271

The tags bellow are tags that were initially created for presentation purposes, but have since been giving a semantic meaning:

`<b>` - used to draw attention to a text, without conveying extra importance. Something you want to highlight without making it important.

`<i>` - used to indicate text that if spoken would have a different tone, voice or mood from the rest of the document, such as text in a different language, or taxonomy designation.

`<small>` - side comments, such as small prints. Typically disclaimers, legal restrictions, or copyrights. This should be a short text, never a long one.

`<s>` - used to mark a text that is outdated and/or no longer relevant, but not a text that were removed from the document (in this case use `<del>`).

It is important to notice that browsers will, for the most part, style such elements as they were originally intended, but you can override their styles with ***CSS***.

## Proper Use of Non-Semantic HTML

In a perfect world we would write our document using only semantic markup and use ***CSS*** rules to style it the way we want. But no, we do not leave in a perfect world (at least I don't) and when time comes to style our pages and elements, we sometimes needs to adjust our content around non-semantic markup to aid visual presentation.

Two of the most common tags used for these purpose are:

`<div>` - generic block container element that does not represent anything.

`<span>` - generic inline container element that does not represent anything.

Use these element for the purpose of aiding on styling and improving accessibility (check **WAI-ARIA** section bellow)

## Common Practices

- Don't wrap all group of links in a `<nav>` element, the `<nav>` element is primarily intended for sections that consist of major navigation blocks. A good use would be for: primary and secondary navigation, or in-page navigation; a redundant use would be: pagination, fat footer, social links, tags, categories.

- Contrary to earlier versions of ***HTML5*** where it specified that developers could and should specify the heading levels per section content, as such it could have multiple `<h1>` headings on the same page, you should instead follow the updated specs that are pretty much aligned with ***HTML4*** where headings defining the hierarchy of the overall page, as such only one `<h1>` per document.

- Do not nest block elements inside of inline elements (e.g: DO NOT: `<a href="some/link"><p>some content</p></a>`)

- Use `<aside>` element for a pull quote (those big excerpts of text from within the current article we highlight to make a point stand out), and `<blockquote>` for actual quotes (content quoted from another source). 

- The `<hr>` element represents a paragraph-level thematic break, something like a transition to another topic within the same section. It should not be used to represent a horizontal line, as it was its previous definitions, even if browsers still render them as such.

- **Anti-pattern** - Using deeply nested divs for page layouts is as much as an anti-pattern as it is to use tables for the same role.

- use `<em>` for normal emphasis where you'd read the emphasized word in a different tone of voice, and `<strong>` for that thing where you take key words and phrases to pick them out of the text to help people skimming the text pick out the subjects.

- `<i>` vs `<em>` - check the discussion at [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em#<i>_vs._<em>)

- `<b>` - check the description at [WHATWG](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-b-element), but in summary the `<b>` tag should be used as a last resort when no other element is more appropriate. In particular, headings should use the `<h1>`..`<h6>`, stress emphasis should use the `<em>`, importance should be denoted with `<strong>`, and text marked or highlighted should use `<mark>`.

- When using either `<i>` or `<b>` tags you should make use of the `class` attribute to identify why the element is being used. (e.g: `<p><b class="lead">lorem ipsum...</b></p>` or `<p>The <i class="taxonomy">Felis silvestris catus</i> is cute.</p>`)

- Use `<button>` to denote action, specially when taken on the same page. use `<a>` (even if it visually resembles a button) when it is just a link to a page where the real action will take place.

- The `<br>` element produces a line break in text, but should not be abused in order to create presentation space between elements. It is useful for writing poems, or addresses, where the division of lines is significant.

- Not every image is a figure, if the image is pure presentational it should not be wrapped in a `<figure>` element. `<figure>` should be used for images that contributes to the context of the document and is self-contained. So your logo should not use `<figure>`. 

## WAI-ARIA

Even all the advances in semantic specification from the current ***HTML*** specification is not enough when it comes to fully accessible web sites or modern web applications.

***WAI-ARIA*** is an independent and complementary specification that is designed to work within ***HTML*** to further aid assistive technologies on understanding the meaning of web pages.

The way you use ***WAI-ARIA*** in your pages are through attributes assigned to elements:

- `role` attribute - improves or overrides the native semantic for a given element, without changing functionality, state, or presentation of such element.

- `aria-*` attributes - defines the state and properties of interactive elements

  e.g.:

      <div role="tab"><h2>heading tab</h2></div>

Rules to follow when deciding to use WAI-ARIA to improve accessibility:

- Only if ***HTML*** doesn't provide the semantic element, or if the semantic element is not yet supported by accessible technologies.

- Do not change native elements semantics unless you really have to, prefer to use non semantic elements such as `<div>` and `<span>`.

- Interactive elements must have keyboard support.

- Do not apply hidden values to elements that are fully visible on the page, this will cause confusion.

- interactive elements must have accessible names

- interactive elements must update ***WAI-ARIA*** attributes to keep it in sync with the state of the element.

### Common WAI-ARIA use:

- `role="presentation"` or `role="none"` - removes the semantic meaning of the element.

- `aria-label`, `aria-labeledby` and `aria-describedby` associates a text content to a subset of interactive elements.

For a full list of roles, properties and states that you can use to improve content accessibility check: [WAI-ARIA ref](https://w3c.github.io/using-aria/#html5na).

## Good References:

- http://html5please.com/
- http://caniuse.com/
- https://platform.html5.org/

## Article References

- https://html.spec.whatwg.org
- https://www.w3.org/TR/html53
- https://www.w3.org/TR/html-aria
- https://developer.mozilla.org/en-US/docs/Web/Guide/HTML
- https://internetingishard.com/html-and-css/semantic-html
- http://loxeo.click/case-studies/post/use-and-abuse-of-non-semantic-tags-in-html-development.html
- http://www.hongkiat.com/blog/html-5-semantics
- http://blog.teamtreehouse.com/use-html5-sectioning-elements
- https://www.cs.tut.fi/~jkorpela/html/em.html
- https://www.codeschool.com/beginners-guide-to-web-development/semantic-html
- https://stackoverflow.com/questions/26883406/how-to-use-section-and-article-tags-in-html5/26887006#26887006
- https://css-tricks.com/document-outline-dilemma
- https://quinnlabs.com/articles/pullquotes-blockquotes-and-asides-in-html5

## Group Activitie

### Intro (Emphasis & Headings)

Using ***HTML***, markup the following:

- https://www.webdesignerdepot.com/cdn-origin/uploads/2009/03/winnie.jpg
- https://www.webdesignerdepot.com/cdn-origin/uploads/2009/03/waqas.jpg
- http://news.bbc.co.uk/1/hi/scotland/north_east/7101506.stm
- http://www.topdesignmag.com/wp-content/uploads/2011/02/275.png
- https://s3.amazonaws.com/ceblog/wp-content/uploads/2011/11/clockbeta.jpg
- https:a//s3.amazonaws.com/ceblog/wp-content/uploads/2011/11/sellfy.jpg
- http://www.christhurman.com/

### Entire Page

Using ***HTML***, markup the following:

- http://sellfy.com/


