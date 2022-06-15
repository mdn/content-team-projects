---
title: Creating, moving, and archiving pages
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
This article describes the guidelines when you want to copy, move, or archive content on MDN Web Docs.

## Copying content from within MDN Web Docs

Sometimes, you might need to reuse the same text on multiple pages (or you might want to use one page's content as a template for another page).
The three scenarios are described below:
<!--this needs to be updated to how we do things on Github-->
### To copy an entire page
<!--Github steps needed-->

  1. While viewing the page you want to copy, on the **Advanced** (gear) menu, choose  **[Clone this page](/en-US/docs/MDN/Contribute/Howto/Create_and_edit_pages#clone_of_an_existing_page)**.
     This opens the editor UI for a new page, with the contents of the cloned page already populated.
  2. Enter a new **Title** and **Slug** for the cloned page.
  3. Edit the contents of the page as needed, and save as usual.

### To copy just part of a page
<!--Github steps needed-->

Don't just visit the page and copy from it. This introduces unwanted additional bits of HTML into the destination page, and somebody will have to clean that up, you or another editor.
  Nobody wants that.
  To copy part of an MDN page to another page:

  1. On the source page, click the **Edit** button on the source page.
  2. **Copy the content you want to reuse from within the editor UI.**
  3. Click **Discard** to exit the editor UI for that page.
  4. Open the editor UI for page where you want to paste.
  5. Paste the content from the clipboard.

  > **Note:** Chrome does not generally include the classes applied to content when copying and pasting across documents in our editor.
  > You need to review the content after doing this and re-apply the lost styles.
  > Check tables, syntax boxes, syntax highlighting, and hidden sections of content in particular.

- Sometimes you literally want to use the same content on many pages.
  In this case, you might be best off placing the content in one page, then using the [`page`](https://github.com/mdn/yari/blob/main/kumascript/macros/page.ejs) macro to transclude the material from one page into another.
  This way, whenever the text on the source page is updated, the destination page will update as well (that is, this will happen on a forced-refresh or when the target page goes through a scheduled rebuild).

## Copying content from elsewhere
<!---not sure if this still holds true--->

Often, there is useful content about a topic somewhere on the web besides MDN Web Docs.
However, copying such content can be fraught with difficulties, both technical and legal.

On the technical level, search engines typically penalize a site in their rankings for reproducing content available elsewhere.
Therefore, it is preferable to have original content on MDN Web Docs to enhance the search engine ranking of MDN Web Docs' content.
You can link to the existing content from MDN Web Docs.

On the legal level, you must be authorized to contribute the content, and it must be licensed and attributed in a way that is compatible with [MDN's license](/en-US/docs/MDN/About#copyrights_and_licenses). <!--- links to be revisited--->

- **If you created the existing content** (for your own purposes and not as work-for-hire), and you are willing to contribute it to MDN Web Docs under MDN's license, this is the easiest case, and you are free to contribute the content.
- **If the copyright for the content belongs to someone else**, it must be licensed and attributed compatibly with MDN's license.
  It is often not easy for someone who is not a lawyer to determine what licenses are compatible.
  To be on the safe side, contact a member of the [MDN Web Docs team](https://github.com/mdn/mdn-community/discussions), who may consult Mozilla's Legal team for guidance if necessary.
  

## How to delete a page

A page should be deleted if it fits the above description. When thinking about deleting pages, you should discuss it with the MDN Web Docs team first. You can communicate with the MDN Web Docs team and community through our [Matrix channel](https://wiki.mozilla.org/Matrix), forums on [Discourse](https://discourse.mozilla.org/c/mdn/236), and discussions on [GitHub](https://github.com/mdn/mdn-community/discussions).

## Guidelines on what can be removed and when

A page should be deleted if it fits the above description.

Sometimes during the development of a new specification or over the course of the evolution of living standards such as HTML, new elements, methods, properties, and so forth are added to the specification, kept there for a while, and then removed. Sometimes this happens very quickly, and sometimes these new items remain in the specification for months or even years before being removed. This can make it tricky to decide how to handle the removal of the item from the specification.

Here are some guidelines to help you decide what to do when something is removed from the specification.

> **Note:** For the purposes of this discussion, the word "item" is used to mean anything that can be part of a specification: an element or an attribute of an element, an interface or any individual method, a property, or other member of an interface, and so forth.

### If the item was never implemented

If the item was _never_ implemented in a release version of _any_ browser, not even behind a preference or a flag, delete any references to the item from the documentation.

- If the item has any documentation pages describing only that one item (such as {{domxref("RTCPeerConnection.close()")}}), delete that page.
    If the removed item is an interface, this means removing any subpages describing the properties and methods on that interface as well.
- Remove the item from any lists of properties, attributes, methods, and so forth. For methods of an interface, for example, this means to remove it from the "Methods" section on the interface's overview page.
- Search the text of the overview page for that interface, element, etc., for any references to the removed item. Remove those references, being sure not to leave weird grammar issues or other problems with the text. This may mean not just deleting words but rewriting a sentence or paragraph to make more sense. It may also mean removing entire sections of content if the description of the item's use is lengthy.
- Similarly, look for any discussion of the item in the guides and tutorials about the relevant API or technology. Remove those references, being sure not to leave weird grammar issues or other problems with the text. This may mean not just deleting words but rewriting a sentence or paragraph to make more sense. It may also mean removing entire sections of content if the description of the item's use is lengthy.
- Search MDN Web Docs for references to the removed item, in case there are discussions elsewhere. It's unlikely that there are, since if it was never implemented, it's unlikely to be widely discussed. Remove those mentions as well.
- If the [Browser compatibility data repository's](https://github.com/mdn/browser-compat-data) JSON files contain data for the removed items, delete those objects from the JSON code and submit a PR with that change, explaining the reason in the commit message and the PR description. Be careful to check that you don't break the JSON syntax while doing this.

### If the item was implemented in a browser behind a flag

If the item was implemented in any release version of any one or more browsers but _only_ behind a preference or a flag, do not delete the item from the documentation immediately. Instead, mark the item as **deprecated** as follows:

- If the item has any documentation pages describing only that one item (such as {{domxref("RTCPeerConnection.close()")}}), add the [`deprecated_header`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Header.ejs) macro to the top of the page and add the {{tag("Deprecated")}} tag to the page's list of tags.
- On the overview page for the element, interface, or API, find the list of items that includes the item that's been removed from the specification and add the [`deprecated_inline`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Inline.ejs) macro after the item's name in that list. <!---revisit link --->
- Search the informative text of the overview page for that interface, element, etc., for any references to the removed item. Add warning boxes in appropriate places with text along the lines of "\[item] has been removed from the specification and will be removed from browsers soon. See \[link to page] for a new way to do this."
- Similarly, look for any discussion of the item in the guides and tutorials about the relevant API or technology. Add similar warnings.
- Search MDN Web Docs for references to the removed item, in case there are discussions elsewhere. Add similar warning boxes there as well.
- At some point in the future, a decision may be made to actually remove the item from the documentation; we don't normally do this but if the item was especially unutilized or uninteresting, we may decide to do so.
- Update any relevant entries in the [Browser Compatibility Data repo](https://github.com/mdn/browser-compat-data) to reflect the obsolescence of the item(s) affected.

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
