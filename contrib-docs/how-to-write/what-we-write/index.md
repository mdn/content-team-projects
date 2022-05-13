---
title: What we write
slug: <MDN/Contribute/how-to-write/what-we-write>
tags:
  - <Guide>
  - <Guidelines>
  - Writing
  - Documentation
  - MDN Meta
---
<{{MDNSidebar}}>

MDN Web Docs contains _browser-neutral_ documentation that enables web developers to write _browser-agnostic_ code. In this article, you'll find information about whether or not a given topic and/or type of content should be included on MDN Web Docs.

> **Note:** Be aware that all contributions to MDN Web Docs fall under specific open source licenses; these are [described in detail](/en-US/docs/MDN/About#copyrights_and_licenses) on our [About MDN](/en-US/docs/MDN/About) page. Keep in mind that Mozilla's [Websites & Communications Terms of Use](https://www.mozilla.org/en-US/about/legal/terms/mozilla/) are in effect when you use or contribute to MDN Web Docs. <!--- links need to be revisited--->

## Topics that belong on MDN Web Docs

In general, if it's an open web technology, we document it on MDN Web Docs. This includes any feature that can be used by web developers to create websites and applications, now and in the near future.

If a feature is implemented by multiple browsers and either accepted as standard or is progressing towards standardization, then yes, we definitely document it here. If a feature is still very experimental and not implemented in multiple browsers and/or liable to change, then it is still suitable for inclusion, but may not be seen as a priority for the writer's team to work on.
<!-- need to follow up on Ruth's feedback here: https://github.com/mdn/content-team-projects/pull/20#discussion_r865151254 -->

In other words, web technologies to be documented on MDN Web Docs should fulfil the following criteria:

- Be on a standards track.
- Be specified in a specification published by a reliable standards body.
- Be implemented by at least one rendering engine.

Variations in browser support are documented in the [browser compatibility](/en-US/docs/MDN/Structures/Compatibility_tables) section of an article. <!--- check for update in link to Structures/Compatibility_tables --->

Our primary focus is to write about the following front-end web technologies:

- [HTML](/en-US/docs/Web/HTML)
- [CSS](/en-US/docs/Web/CSS)
- [JavaScript](/en-US/docs/Web/JavaScript)
- [Web APIs](/en-US/docs/Web/API)

We also document some broader topics, such as [SVG](/en-US/docs/Web/SVG), [XML](/en-US/docs/Web/XML), [WebAssembly](/en-US/docs/WebAssembly), and [Accessibility](/en-US/docs/Learn/Accessibility). In addition, we provide extensive [learning guides](/en-US/docs/Learn) for these technologies and also a [glossary](/en-US/docs/Glossary).

> **Note:** Backend technologies usually have their own documentation elsewhere that MDN Web Docs does not attempt to supersede, although we [do have some exceptions](/en-US/docs/Learn/Server-side).

All content on MDN Web Docs must be relevant to the technology section in which it appears. Contributors are expected to follow the [MDN guidelines](/en-US/docs/MDN/Guidelines) for writing style, code samples, and other topics. <!--- link needs to be revisited--->

For more details on acceptance criteria for whether or not a technology can be documented on MDN Web Docs, see the [Criteria for inclusion]<!--- add link--->

## Topics that don't belong on MDN Web Docs

In general, anything that isn't an open web standard does not belong on MDN Web Docs. Spam (commercial advertisement) and other irrelevant content will never be accepted into the site. Contributors who keep trying to submit spam may be banned from MDN at the discretion of Mozilla MDN staff.

Examples of inappropriate topics for MDN Web Docs include:

- Technology that is not exposed to the web and is specific to a browser.
- Technology that is not related to the web.
- Documentation for end-users. For Mozilla products, for example, such documentation belongs on the [Mozilla support site](https://support.mozilla.org).
- Self-linking or self-promoting external links. Check out these guidelines before adding an external link. <!--- add link to guidelines for external links --->

## Types of documents that belong on MDN Web Docs

In general, MDN Web Docs is for _product_ documentation, not for _project_ or _process_ documentation (except [about MDN itself](/en-US/docs/MDN)). So, if the document is about "how to use a thing" or "how a thing works" (where, the "thing" is in one of the topic categories mentioned above), then it can go on MDN Web Docs. But if it is about "who's working on developing a thing" or "plans for developing a thing", then it shouldn't go on MDN Web Docs. In that case, if the thing is being developed under the umbrella of Mozilla, then the [Mozilla project wiki](https://wiki.mozilla.org/Main_Page) may be a good place for it.

Here are some examples of types of documents that should _not_ be placed on MDN Web Docs:

- Planning documents
- Design documents
- Project proposals
- Specifications or standards
- Promotional material, advertising, or personal information

## Terms used on MDN Web Docs to label a technology

<!--content copied from /en-us/mdn/guidelines/conventions_definitions -->

These terms are commonly associated with technologies and specifications. These are also defined in our [Browser compatibility project](https://github.com/mdn/browser-compat-data/blob/main/schemas/compat-data-schema.md#status-information).

### Deprecated

The term **deprecated** on MDN Web Docs is used to mark an API or technology that is no longer recommended. A deprecated API or technology might be removed in the future or might only be kept for compatibility purposes and may still work. We recommend to avoid using the functionality marked as deprecated.

### Obsolete

On MDN Web Docs, the term **obsolete** was used to mark an API or technology that is not only no longer recommended but is also no longer implemented in browsers. The term was, however, confusing. It was similar to **deprecated** but it's distinction from **deprecated** ws not very helpful.

> **Note:** We do not use the term **obsolete** on MDN Web Docs anymore. If you come across any instances, they should be removed or replaced with the term **deprecated**.

### Experimental

The term **experimental** can mean different things depending on the context you hear or read it in.
When a technology is described as experimental on MDN Web Docs, it means that the technology is nascent and immature and is currently _in the process_ of being added to the web platform (or being considered for addition).

For a technology that's marked **experimental**, one or both of the following conditions will be true:

- It is implemented and enabled by default in _less than two_ modern major browsers.
- Its defining specification is likely to change significantly, in backwards-incompatible ways (i.e., it may break existing code that relies on the feature).

If one or both of these conditions is true, then you should think carefully before you start using that technology in any kind of production project (i.e., a project that is not just a demo or experiment). On the other hand, as a web developer, you can try out a feature that is marked **experimental** and provide feedback to browser vendors and standards authors. <!--taken from https://github.com/mdn/browser-compat-data/blob/main/schemas/compat-data-schema.md#status-information -->

Conversely, a technology is no longer considered **experimental** if one of the following conditions is true:

- It is implemented in two or more major browsers.
- Its defining specification is unlikely to change in ways that will break the web.

Usually, if a technology is supported across several major browsers, the specification will be stable, but this is not always the case.
And some technologies might have a stable specification and be well-used but might not have native support in browsers ([IMSC](/en-US/docs/Related/IMSC), for example). <!-- need to revisit link -->

A feature or technology that is not marked **experimental** or **deprecated** is said to be on a **standards track**, meaning the feature is part of an active specification or specification process.
