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
  