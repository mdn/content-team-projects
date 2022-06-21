---
title: How to write for MDN
slug: MDN/Writing_guidelines/How_to_write
page-type: mdn-writing-guide
tags:
  - meta
  - writing-guide
---
{{MDNSidebar}}

This section of MDN Web Docs writing guidelines contains all the information on *how* to approach **writing** for MDN. The different types of pages we have, what is included in them, how we use markdown, code example guidelines and more.

To find out more about _how to contribute_ (which happens through GitHub) please refer to our [community guidelines]().

> **Note:** All the way through this section we assume you have read the contribution guidelines and are familiar with the mdn/content repository and how to use git and GitHub.

MDN Web Docs content is primarily held in the mdn/content repository and each page is written in a markdown format with frontmatter information at the top.

Some content is held in other repositories; primarily code examples (such as interactive-examples at the top of pages). Anything related to the platform (the website itself and _not_ the articles) is held within the mdn/yari repository.

If you're looking for the place to update the browser compatibility tables, that data is held with mdn/browser-compat-data repository.




## Editing an existing page

To edit a page, you need to find the page source in our [content](https://github.com/mdn/content) repo. The easiest way to find it is to navigate to the page you want to edit, go to the bottom of the page, and click on the "Source on GitHub" link.

Once you've found the source to edit, go to our README and work through our [Making contributions](https://github.com/mdn/content#making-contributions) guide.

### Preview changes

If you are editing the page locally, to see what your changes look like you can go to the content repo folder, execute the CLI command `yarn start`, go to `localhost:5042` in your browser, and navigate to page and view it. Enter the title in the search box to find it easily. The previewed page will update in the browser live as you edit the source.

### Tags

You can add or remove tags, which describe the page's content and purpose, in the "tags" list at the top of the page source. See [How to properly tag pages](/en-US/docs/MDN/Contribute/Howto/Tag), for information on which tags to apply.

### Attach files

To attach a file to your article, you just need to include it in the same directory as the article's `index.html` file, and include it in your page, typically via an `<a>` element.

## Creating a new page

To create a new page, see our [Adding a new document](https://github.com/mdn/content#adding-a-new-document) instructions.

## See also

- [MDN style guide](/en-US/docs/MDN/Guidelines/Writing_style_guide)

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

### If the item was implemented in a browser without a flag

If the item was implemented in one or more release builds of browsers without requiring a preference or a flag, mark the item as **deprecated**, as follows:

- If the item has any documentation pages describing only that one item (such as {{domxref("RTCPeerConnection.close()")}}), add the [`deprecated_header`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Header.ejs) macro to the top of the page and add the {{tag("Deprecated")}} tag to the page's list of tags.
- On the overview page for the element, interface, or API, find the list of items that includes the item that's been removed from the specification and add the [`deprecated_inline`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Inline.ejs) macro after the item's name in that list.
- Search the informative text of the overview page for that interface, element, etc., for any references to the removed item. Add warning boxes in appropriate places with text along the lines of "\[item] has been removed from the specification and is deprecated. It may be removed from browsers in the future, so you should not use it. See \[link to page] for a new way to do this."
- Similarly, look for any discussion of the item in the guides and tutorials about the relevant API or technology. Add similar warnings.
- Search MDN Web Docs for references to the removed item, in case there are discussions elsewhere. Add similar warning boxes there as well.
- It's unlikely that these items will be removed from the documentation anytime soon, if ever.
- Update any relevant entries in the [Browser compatibility data repository](https://github.com/mdn/browser-compat-data) to reflect the deprecation of the item(s) affected.

Please use common sense with wording of warning messages and other changes to the text suggested in the guidelines above.
Different items will require different wording and handling of the situation.
When in doubt, feel free to ask for advice on the [MDN Web Docs chat room](https://chat.mozilla.org/#/room/#mdn:mozilla.org) on [Matrix](https://wiki.mozilla.org/Matrix), or on the [MDN Web Docs discussion forum](https://discourse.mozilla.org/c/mdn).

## How to communicate a specification conflict

Sometimes, but rarely, there might be a conflict between different specification versions (usually W3C versus WHATWG). For example, one version might have a feature listed as deprecated, while the other doesn't.
In such cases, consider what the reality is, that is, consider what browsers are actually doing, and write an "important" note to summarize that latest status.
For example, as of Jan 2019, the [`inputmode`](/en-US/docs/Web/HTML/Global_attributes/inputmode) global attribute has a conflict, which was summarized like so: <!--this warning example for spec conflict does not exist anymore on that page. couldn't find any other examples as well -->

> **Warning:** Specification conflict: The WHATWG specification lists `inputmode`(https://html.spec.whatwg.org/multipage/interaction.html#attr-inputmode) and modern browsers are working towards supporting it.
> The [W3C HTML 5.2 spec](https://html.spec.whatwg.org/multipage/index.html#contents), however, no longer lists it (i.e. marks it as obsolete).
> You should consider the WHATWG definition as correct, until a consensus is reached.





