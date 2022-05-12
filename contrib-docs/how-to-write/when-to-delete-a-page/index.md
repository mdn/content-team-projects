---
title: When to delete a page
slug: 
tags:
  - Documentation
  - Guide
  - Guidelines
  - MDN
  - MDN Meta
---
{{MDNSidebar}}

<!-- content copied from /en-us/mdn/guidelines/conventions_definitions -->

### Archived pages

Archived pages are pages that are stored in the MDN [Archive of obsolete content](/en-US/docs/Archive).
These pages contain information out-of-date enough that it is not directly useful to anyone anymore.

Most commonly, these concern Mozilla projects that have been discontinued and shouldn't be relied on anymore.
But we don't delete them because they form a useful historical record, and some of the patterns or ideas contained within might be useful for future work.
A good example is the [B2G (Firefox OS) project](/en-US/docs/Archive/B2G_OS).

#### When should a page be archived?

A page should be archived if it fits the above description.
To archive a page, you should use the "Move page feature" (_Advanced > Move this article_) to move the page into the Archive page tree (/en-US/docs/Archive).
You might not have the permissions to use this feature, and before you start archiving pages you should discuss it with the MDN community first — talk to us on our [Discourse forum](https://discourse.mozilla.org/c/mdn/236).

### Deleted pages

Deleted pages are pages that have been explicitly deleted from MDN — see for example the [`SharedKeyframeList`](/en-US/docs/Web/API/SharedKeyframeList) interface and [`SharedKeyframeList()`](/en-US/docs/Web/API/SharedKeyframeList/SharedKeyframeList) constructor.
These pages contain information that is not useful in any way anymore, and/or might be incorrect to the point where keeping it available might be confusing or bad for people to know.

These might be:

- Reference pages for API features that were removed from the specification before they were implemented in any browsers.
- Articles covering techniques that were later shown to be bad practice and superseded by better techniques.
- Articles containing information that were later replaced by other, better quality articles.
- Articles containing content that is inappropriate for MDN.
- Translations that are old, out-of-date, and difficult to fix, meaning that the English version is preferable and starting a new translation would be an easier option.

#### When should a page be deleted?

A page should be deleted if it fits the above description.
To delete a page, you should use the "Delete this page feature" (_Advanced > Delete this page_) to delete the page.
You will probably not have the permissions to use this feature, and when thinking about deleting pages you should discuss it with the MDN community first — talk to us on our [Discourse forum](https://discourse.mozilla.org/c/mdn).

## Conventions

### When something is removed from the specification

Sometimes during the development of a new specification, or over the course of the evolution of living standards such as HTML, new elements, methods, properties, and so forth are added to the specification, stay there for a while, then get removed again.
Sometimes this happens very quickly, and sometimes these new items remain in the specification for months or even years before being removed.
This can make it tricky to decide how to handle the removal of the item from the spec.
Here are some guidelines to help you decide what to do.

> **Note:** For the purposes of this discussion, the word "item" is used to mean anything which can be part of a specification: an element or an attribute of an element, an interface or any individual method, property, or other member of an interface, and so forth.

- If the item was _never_ implemented in a release version of _any_ browser—even behind a preference or flag—delete any references to the item from the documentation.

  - If the item has any documentation pages describing only that one item (such as {{domxref("RTCPeerConnection.close()")}}), delete that page.
    If the removed item is an interface, this means removing any subpages describing the properties and methods on that interface as well.
  - Remove the item from any lists of properties, attributes, methods, and so forth.
    For methods of an interface, that means to remove it from the "Methods" section on the interface's overview page, for example.
  - Search the text of the overview page for that interface, element, etc. for any references to the removed item.
    Remove those references, being sure not to leave weird grammar issues or other problems with the text.
    This may mean not just deleting words but rewriting a sentence or paragraph to make more sense.
    It may also mean removing entire sections of content if the description of the item's use is lengthy.
  - Similarly, look for any discussion of the item in the guides and tutorials about the relevant API or technology.
    Remove those references, being sure not to leave weird grammar issues or other problems with the text.
    This may mean not just deleting words but rewriting a sentence or paragraph to make more sense.
    It may also mean removing entire sections of content if the description of the item's use is lengthy.
  - Search MDN for references to the removed item, in case there are discussions elsewhere.
    It's unlikely that there are, since if it was never implemented, it's unlikely to be widely discussed.
    Remove those mentions as well.
  - If the [Browser Compatibility Data repository's](https://github.com/mdn/browser-compat-data) JSON files contain data for the removed items, delete those objects from the JSON code and submit a PR with that change, explaining why in the commit message and the PR description.
    Be careful to check that you don't break the JSON syntax while doing this.

- If the item was implemented in any release version of any one or more browsers—but _only_ behind a preference or flag—do not delete the item from the documentation immediately.
  Instead, mark the item as deprecated as follows:

  - If the item has any documentation pages describing only that one item (such as {{domxref("RTCPeerConnection.close()")}}), add the [`deprecated_header`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Header.ejs) macro to the top of the page and add the {{tag("Deprecated")}} tag to the page's list of tags.
  - On the overview page for the element, interface, or API, find the list of items which includes the item that's been removed from the specification and add the [`deprecated_inline`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Inline.ejs) macro after the item's name in that list.
  - Search the informative text of the overview page for that interface, element, etc. for any references to the removed item.
    Add warning boxes in appropriate places with text along the lines of "\[whatever] has been removed from the specification and will be removed from browsers soon.
    See \[link to page] for a new way to do this."
  - Similarly, look for any discussion of the item in the guides and tutorials about the relevant API or technology. Add similar warnings.
  - Search MDN for references to the removed item, in case there are discussions elsewhere.
    Add similar warning boxes there as well.
  - At some point in the future, a decision may be made to actually remove the item from the documentation; we don't normally do this but if the item was especially unutilized or uninteresting, we may decide to do so.
  - Update any relevant entries in the [Browser Compatibility Data repo](https://github.com/mdn/browser-compat-data) to reflect the obsolescence of the item(s) affected.

- If the item was implemented in one or more release builds of browsers—without requiring a preference or flag to be changed—mark the item as deprecated, as follows:

  - If the item has any documentation pages describing only that one item (such as {{domxref("RTCPeerConnection.close()")}}), add the [`deprecated_header`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Header.ejs) macro to the top of the page and add the {{tag("Deprecated")}} tag to the page's list of tags.
  - On the overview page for the element, interface, or API, find the list of items which includes the item that's been removed from the specification and add the [`deprecated_inline`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Inline.ejs) macro after the item's name in that list.
  - Search the informative text of the overview page for that interface, element, etc. for any references to the removed item.
    Add warning boxes in appropriate places with text along the lines of "\[whatever] has been removed from the specification and is deprecated.
    It may be removed from browsers in the future, so you should not use it.
    See \[link to page] for a new way to do this."
  - Similarly, look for any discussion of the item in the guides and tutorials about the relevant API or technology. Add similar warnings.
  - Search MDN for references to the removed item, in case there are discussions elsewhere.
    Add similar warning boxes there as well.
  - It's unlikely that these items will be removed from the documentation anytime soon, if ever.
    It's possible, however, that some or all of the material may be moved to the [Archive](/en-US/docs/Archive) section of the site.
  - Update any relevant entries in the [Browser Compatibility Data repo](https://github.com/mdn/browser-compat-data) to reflect the deprecation of the item(s) affected.

Please use common sense with wording of warning messages and other changes to text suggested by the guidelines above.
Different items will require different wording and handling of the situation.
When in doubt, feel free to ask for advice on the [MDN Web Docs chat room](https://chat.mozilla.org/#/room/#mdn:mozilla.org) on [Matrix](https://wiki.mozilla.org/Matrix), or on the [MDN Web Docs discussion forum](https://discourse.mozilla.org/c/mdn).

#### How to communicate a spec conflict

Note that sometimes (but rarely) there is a conflict between different spec versions (usually W3C versus WHATWG), e.g. one version might have a feature listed as deprecated, while the other doesn't.
In such cases, consider what the reality is — i.e. what browsers are actually doing — and write an "important" note to summarize that latest status.
For example, as of Jan 2019 the [`inputmode`](/en-US/docs/Web/HTML/Global_attributes/inputmode) global attribute has a conflict, which was summarized like so:

> **Warning:** Spec conflict: The [WHATWG spec lists `inputmode`](https://html.spec.whatwg.org/multipage/interaction.html#attr-inputmode), and modern browsers are working towards supporting it.
> The [W3C HTML 5.2 spec](https://html.spec.whatwg.org/multipage/index.html#contents) however no longer lists it (i.e. marks it as obsolete).
> You should consider the WHATWG definition as correct, until a consensus is reached.=