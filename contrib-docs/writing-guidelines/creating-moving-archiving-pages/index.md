---
title: 'Creating, moving, and deleting pages'
slug: MDN/Writing_guidelines
page-type: mdn-writing-guide
tags:
  - meta
  - writing-guide
---
{{MDNSidebar}}

This article describes how to create, move or delete a page. In all instances it's a good idea to check our [What we write](/en_US/docs/MDN/Writing_guidelines/What_we_write) guidelines for whether any of these actions should be taken and discuss it with us before going ahead.

## Creating pages

All pages are authored in markdown format, with the filename `index.md` and their own unique directory. The directory name represents the name of the page. For example to create a new reference page for a new CSS property, you'd create a folder in `en-us/web/css` named with the property name and create a file called `index.md` inside it.

> **Note:** The name of the directory differs slightly from the slug of the page. Most notably the slug is capitalized.

There are lots of different [page types with certain structures](/en_US/docs/MDN/Writing_guidelines/How_to_write/Page_types), and supporting page templates for them, which you can copy to get you started.

A document's `index.md` file must start with front-matter that defines the `title`, `short-title`, `page-type`, `slug`, and `tags`. All of which can be found in the afore mentioned page templates. Alternatively you might find it helpful to refer to the front-matter within a similar document's `index.md`.

The step-by-step process in general would be:

1. Start a fresh, up-to-date branch to work within:

```sh
cd ~/repos/mdn/content
git checkout main
git pull mdn main
# Run "yarn" again to ensure you've
# installed the latest Yari dependency.
yarn
git checkout -b my-add
```

1. Create one or more new document folders, each with their own `index.md` file.

1. Add and commit your new files, as well as push your new branch to your fork:

    ```sh
    git add files/en-us/folder/you/created
    git commit
    git push -u origin my-add
    ```

1. And finally create your
pull request.

## Moving pages

Moving one or more documents, or an entire tree of documents is easy,
because we've created a special command that takes care of the details for you:

```sh
yarn content move <from-slug> <to-slug> [locale]
```

You just have to specify the slug of the existing document that you'd like
to move (e.g., `Learn/Accessibility`), as well as the slug of its new
location (e.g., `Learn/A11y`), optionally followed by the locale of the
existing document (defaults to `en-US`).
If the existing document that you'd like to move has child documents (i.e.
it represents a document tree), the `yarn content move` command will move
the entire tree. For example, let's say you want to move the entire
`/en-US/Learn/Accessibility` tree to `/en-US/Learn/A11y`:

1. First, as we've outlined above, you'll start a fresh branch to work within:

    ```sh
    cd ~/repos/mdn/content
    git checkout main
    git pull mdn main
    # Run "yarn" again just to ensure you've
    # installed the latest Yari dependency.
    yarn
    git checkout -b my-move
    ```

1. Perform the move (which will delete and modify existing files, as well
as create new files):

    ```sh
    yarn content move Learn/Accessibility Learn/A11y
    ```

1. Add and commit all of the deleted, created, and modified files, as well as
push your branch to your fork:

    ```sh
    git commit -a
    git push -u origin my-move
    ```

1. Now you're ready to create your pull request.

> **Note:** `yarn content move` automatically adds the necessary redirect
information to the `_redirects.txt` file so that the old location will redirect
to the new one. Don't edit the `_redirects.txt` file manually!
mistakes can easily creep in if you do. If you need to add a redirect without
moving a file, talk to us about it.

## Deleting pages

Documents should only be removed from MDN in special circumstances. If you are thinking about deleting pages, please discuss it with the MDN team first.

Deleting one or more documents, or an entire tree of documents is also easy,
again because we've created a special command that takes care of the
details for you:

```sh
yarn content delete <document-slug> [locale]
```

You just have to specify the slug of the existing document that you'd like
to delete (e.g., `Learn/Accessibility`), optionally followed by the locale
of the existing document (defaults to `en-US`). If the existing document
that you'd like to delete has child documents (i.e. it represents a
document tree), you must also specify the `-r, --recursive` option, or
the command will fail.

**Important: you need to use the `delete` command to delete MDN documents. Don't
just delete their directories from the repo, as `delete` also handles other
necessary changes such as updating the `_wikihistory.json` file.**

For example, let's say you want to delete the
entire `/en-US/Learn/Accessibility` tree:

1. First, as we've outlined above, you'll start a fresh branch to work in:

    ```sh
    cd ~/repos/mdn/content
    git checkout main
    git pull mdn main
    # Run "yarn" again just to ensure you've
    # installed the latest Yari dependency.
    yarn
    git checkout -b my-delete
    ```

1. Perform the delete:

    ```sh
    yarn content delete Learn/Accessibility --recursive
    ```

1. Add a redirect

```sh
    yarn content add-redirect /en-US/path/of/deleted/page /en-US/path/of/target/page
    ```

    Note that the target page can be an external URL or another page.

1. Add and commit all of the deleted files, as well as
push your branch to your fork:

    ```sh
    git commit -a
    git push -u origin my-delete
    ```

1. Now you're ready to create your pull request.

> **Note:** If the slug of the page you wish to delete contain special
  characters, include it in quotes:

```sh
yarn content delete "Mozilla/Add-ons/WebExtensions/Debugging_(before_Firefox_50)"
```

Removing content from MDN will inevitably result in updating existing content as well, as a lot of articles reference other content, the removed content will be referenced elsewhere.

Here are some guidelines on different circumstances

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
  

