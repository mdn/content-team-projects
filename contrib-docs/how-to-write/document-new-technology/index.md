---
title: Documenting a new technology
slug: 
tags:
  - <Guide>
  - <Guidelines>
  - Writing
  - Documentation
  - MDN Meta
---
<{{MDNSidebar}}>

<!-- content copied from /en-us/mdn/guidelines/conventions_definitions -->
## When to document new technologies

On MDN web Docs, we are constantly looking to document new web standards technologies as appropriate.
We try to strike a balance between publishing the documentation early enough so that developers can learn about new features as soon as they need to and publishing it late enough so that the technology is mature and stable so the documentation won't need constant updates or rapid removal.

In general, our definition of the earliest we'll consider documenting a new technology is:

_"When the feature is on a standards track and is implemented somewhere."_

You should definitely consider documenting a new technology if:

- It is specified in a specification document published under a reliable standards organization (such as W3C, WHATWG, Khronos, IETF, etc.) and has reached a reasonable level of stability (e.g., a W3C working draft or candidate recommendation or when the specification is looking fairly stable judging by the flow of issues filed against it).
- It is implemented consistently in at least one browser, with other browser developers showing signs of interest (such as an active ticket or an "intent to implement" process is in effect).

You should be more wary of documenting a new technology (but should still consider it if it makes sense) if it:

- Doesn't have a specification or the specification is a rough note that looks liable to change.
- One or zero browsers have currently implemented it and non-supporting browsers are not showing signs of interest in implementing it. You can gauge this by asking engineers who work on those browsers and by looking at browser bug trackers and mailing lists, etc.

You should not consider documenting a new technology if it is:

- Not a web-exposed technology and/or is completely proprietary.
- Already showing signs of being deprecated or superseded by a similar feature.

<!--content copied from /en-us/related/criteria_for_inclusion -->

The sections below will help you work out if a non-web standards technology is suitable for inclusion on MDN Web Docs.

## Web standards technologies

The remit of MDN Web Docs is to document web standards technologies that are specified in a specification published by a reliable standards body and are supported in at least one browser. These criteria signal enough interest, stability, and "intent to implement" by the web industry at large. Therefore, we think those technologies are a safe bet for us to spend our time and effort in documenting them. Any earlier than, a web technology or a feature might be prone to getting cancelled due to lack of interest or might be so unstable that it might change significantly, which will needlessly involve lot of rewriting (which we try to avoid where possible).

## Non-web standards technologies

Non-web standards technologies are technologies that do not follow our criteria summarized above. We would not normally consider them for documentation on MDN Web Docs. However, there are many technologies that are not web standards but are useful and interesting to web developers — think about libraries and frameworks as some of the more obvious examples. <!-- can we give other examples or links on mdn here?-->

Our mission statement is _"to provide developers with the information they need to easily build projects on the open web"_. This suggests that we should consider documenting technologies that are useful to web developers, even if they are not open web standards, on the standards track, etc.

If you want to consider a non-web standard technology for inclusion on MDN Web Docs, you should make sure that it matches the criteria below.

## Criteria for inclusion on MDN Web Docs

Technologies should fulfill the criteria described here for being considered to be documented on MDN Web Docs.

### Be open and not proprietary

At MDN Web Docs, we are supporters of open technologies. We don't support closed technology ecosystems that are controlled by a single entity, that are not open for contributions by any interested party, and that are not interoperable across multiple platforms and systems. We believe that technology works better for everyone when created out in the open.

### Be web-exposed and be related to web technologies

Our central remit is web standards technologies; there is no point starting to document technologies that do not relate to the web or hold any interest to web developers.

### Show signs of interest and adoption

We don't want to spend our time documenting a technology that has no signal of interest and adoption from the industry. It may just be that it is too early to start documenting the technology, and we could consider it to be documented on MDN Web Docs in the future.

### Not show signs of being deprecated or superseded

Related to the above point, we also don't want to spend our time documenting a technology that is late in its lifecycle and is already showing signs of decline in interest.

### Not have an established documentation resource elsewhere

There are many libraries and frameworks in existence, which are not web standards but are built on top of web technologies and are very popular in the web industry. We do not document any of these, because in general, they all have established documentation resources already. It would be foolish to compete with the official resource of a popular framework — to do so would be a waste of time and probably end up confusing developers trying to learn the technology. <!-- to keep or not keep this last sentence? -->

### Have a community willing to write and maintain the documentation

The MDN Web Docs team concentrates on documenting the open web platform. If you want a technology in this area to be considered for documentation on MDN Web Docs, you'll need to have a community assembled that is willing to write the documentation and maintain it after completion. Our team is happy to provide guidance in such cases, including edits and feedback, but we don't have time for much more than that.

<!--content copied from /en-us/related/process_for_selection -->

## Process for selecting the new technology

If a technology looks like a good candidate for being documented on MDN Web Docs, you can contact the team to propose and discuss the inclusion of this technology. This section describes what the proposal should include and how to contact the team.

### Submitting the proposal

Non-web standards technologies will be considered for inclusion on MDN Web Docs on a case-by-case basis. For consideration, you would need to submit a proposal titled "Proposal for documenting a new technology on MDN Web Docs". We would need the following information from you in the proposal:

- The technology, its core purpose/use cases, and target developer audience.
- What kind of industry or community buzz is there is around the technology?
  For example:

  - Are a lot web developers using it? What is the industry adoption like?
  - Do a lot web developers want or need this information?
  - What is the size of the target audience size for this information? Supporting statistics would help, if you have them.
  - How does the technology relate to core web technology and web browsers? Useful details include:
    - Does it use HTML and CSS but generally not output to the web?
    - Is it supported in web browsers via a polyfill?
- What documentation or resources are already available that cover the technology?
- How much documentation would need to be added to MDN Web Docs?
  - List the expected number of guides, tutorials, reference pages for elements/methods/attributes, etc.
  - Provide a high-level table of contents.
  - Mention the kind of "advanced" features you think you might need for this resource, beyond the basic documentation pages. Are you expecting to include embedded videos, interactive code samples, etc.?

- Who will be writing the documentation? Who are they and why are they suited for the job?

You don't need to provide us with hundreds of pages of detail at this stage (in fact, we'd prefer it if you didn't). A couple of paragraphs on each of the above points is more than adequate.

> **Note:** MDN Web Docs is primarily an English site (en-US). The primary language for your project should be in US English. If this really doesn't make sense for your project (e.g., it might be for a tool that is usable in a specific non-English locale), then mention this in your proposal. we'll see how we can accommodate this.


You can submit your proposal in our [public discussion forum](https://github.com/mdn/mdn-community/discussions) on Github. <!-- can we also specify a category where to open such a discussion? "Content suggestions"? -->

### Awaiting a response

We will consider the technology and respond with one of the following answers:

- **No**: We don't think this meets the criteria for being documented on MDN Web Docs.
- **Maybe**: We are not sure if it is suitable for documenting on MDN Web Docs and would like to ask some further questions.
- **Yes**: We think it is appropriate for including it on MDN Web Docs.
<!--we can discuss if this is how we are really going to respond - using one of those three options -->
The MDN Web Docs team will interact with you in our [public discussion forum](https://github.com/mdn/mdn-community/discussions) on Github. If the technology is a good candidate, the team will assist you in getting started with the documentation.

<!--content copied from /en-us/related/project_guidelines -->
## Project guidelines for documenting the new technology

If your chosen technology is accepted for documentation on MDN Web Docs, the next step is to get started.

To ensure that your project for documenting the new technology on MDN Web Docs is successful, we'll need you to have the following in place:

- A dedicated team
- A project plan and roadmap
- Writing guidelines and standards
- An intuitive documentation structure
- A maintenance plan

### Dedicated team

Make sure you have a dedicated team in place that will be there to both write the initial documentation as well as maintain it in future with the required updates.

Have a think about how much work there is and how many people you might need for that.

If it is a large project, you might benefit from having a few writers, a technical reviewer to check that the work is technically accurate, a copy editor to clean up the language, someone to write code examples, etc.

On a smaller project, you might have one or two people taking on multiple roles. However you want to build up the team is fine as long as it works for you.

A member of the MDN Web Docs team will be assigned to your project to provide guidance on the MDN Web Docs side of things.

You should assign one (or two) team leads who can liaise with the MDN Web Docs team member.

The MDN Web Docs representative will help get the required permissions to everyone on your team to work in the [MDN organization on Github](https://github.com/mdn).

### Project plan and roadmap

Create a plan for the project — tasks, estimate completion dates, and milestones you would want to track to ensure you're making steady progress.

If the project is large, you should consider assigning one of your team members as the project manager and using a project tracking tool like [Trello](https://trello.com/). You should also consider writing a sub-project plan for an initial release that encompasses the minimum set of documentation that is useful to publish (a _minimum viable product_); you can follow it up with further additions later.

If the documentation project is small, you would still need to keep a record of what has been done and what hasn't, what stage each part of the documentation is at (e.g., not started, in progress, draft written, reviewed, done), and who is working on what.

### Writing guidelines and standards

There are [guidelines available](/en-US/docs/MDN/Guidelines) that state how we expect documents to be written for MDN Web Docs.  <!--- link to be revisited —-->

Since this is a project in its own right, you may have additional guidelines on language or code styles that you expect to be followed. Feel free to keep a record of these, and even host them on a page inside your own project pages.  <!--- I guess we delete this? —-->

In terms of standards, you are expected to maintain a reasonable level of writing quality for your documentation to stay on MDN Web Docs. Your MDN Web Docs representative will work with you to make you clear on what is expected. It is a good idea to produce a prototype showing what each type of page in your documentation would look like (e.g., an element or method reference page, a code example, etc.) so that your team has a template to follow.

> **Note:** MDN Web Docs is primarily an English site (en-US). The primary language for your project should be in US English. If this really doesn't make sense for your project (e.g., it might be for a tool that is usable in a specific non-English locale), then mention this in your proposal. we'll see how we can accommodate this.
<!--- there note is also in the proposal part —-->

### Intuitive documentation structure

If you went through the proposal submission process then you should already have a rough outline of what you are going to write for this technology. At this point you should refine that into a site structure plan: think about what the document hierarchy will be and where everything will fit and link together.

Each project is different, but we'd roughly recommend something like this:

```
Landing page
|
------Reference
      |
      --------Elements
      |
      --------Methods
      |
      --------Other reference page type(s)?
|
------Guides/tutorials
|
------Examples
|
------Project metadata
```

Each page type that you will use in your project should have a page template for others to copy the structure from. You should decide on these early on.
<!--- should we keep this section here or just direct readers to our page types documentation instead? --->

<!--- not edited landing page, reference pages, and guides/tutorials. will need to be edited in case we decide to keep them here --->
#### Landing page

The landing page should contain something like:

- Introductory paragraph to say what the technology is and why it's exciting.
- Concepts and usage — why the technology exists, use cases, target audience, and a brief description of how it is used. This should be a taster, and not too much detail. If there is a lot to say here, feel free to spin it out to a separate "Concepts" article that can live in the Guides/tutorials section.
- List of reference docs, guides, and examples — list these in separate sections, with links and descriptions of what they do. For code examples, you can show code snippets in your pages, but you are also advised to create some kind of repo to contain full examples for people to learn from, on [GitHub](https://github.com/) for example.
- Specifications — it is useful to link to specifications and other such documents that define and provide context to the technology.
- Project team — in this section, list the project team and their contact details. It is useful for the MDN team to know who is responsible for a project at a glance, as well as external people who might want to provide feedback or help with the documentation work.
- See also — in here, include any other links you think might be useful.

#### Reference pages

Each reference page type should have a template defined. These will likely be different in structure to the reference page types you see on the core MDN site, but that's OK. Feel free to use our pages for guidance/inspiration, and talk to your MDN rep for help.

#### Guides/tutorials

The structure of guides/tutorials can be anything you like, as long as it proves effective in teaching readers what they need to know. Again, feel free to look to some of our guides for inspiration.


### Maintenance plan

The documentation for this technology  will need to be maintained to remain on MDN Web Docs:

- The content and files for MDN Web Docs are stored on Github. When others make changes to the documentation for your technology, a member from your team needs to review those changes to make sure the content is still good. You can track the open pull requests (PRs) via Github's notification feature.
- When changes occur to the technology that require documentation to be updated, your team needs to make updates as appropriate, maintaining the same standards as the original documentation.

If positive changes are not observed over a period of 6 months and the documentation appears to be:

- Stale or unmaintained
- Stalled without being finished
- Low quality
- Becoming obsolete

Then the documentation for this technology will be considered dead. After a discussion between your team and the MDN Web Docs team representative, the documentation will be removed.

We hope you understand that we need to be strict on such matters — we can't let the site fill up with bad quality, incomplete, or obsolete documentation — it harms our reputation.
