---
title: Documenting a new technology
slug: <MDN/Contribute/how-to-write/what-we-write>
tags:
  - <Guide>
  - <Guidelines>
  - Writing
  - Documentation
  - MDN Meta
---
<{{MDNSidebar}}>

<!--content copied from /en-us/related/criteria_for_inclusion -->

## Criteria for inclusion on MDN Web Docs

This document outlines the criteria for inclusion that a technology must pass before we will consider it for inclusion in the MDN Web Docs [Web-related technologies](/en-US/docs/Related) section. The aim here is to provide a guide you can follow to quickly work out if a non-web standards technology is suitable for inclusion.

## Web standards technologies

The MDN Web Docs remit is to document web standards technologies, or more specifically technologies that follow our standard guidelines of [when to document new technologies](/en-US/docs/MDN/Guidelines/Conventions_definitions#when_to_document_new_technologies) — the short version of this is that we document technologies on MDN Web Docs when they are specified in a specification published by a reliable standards body, and are supported in at least one browser.

These criteria signify enough interest, stability, and intent to implement by the web industry at large that we think they are a safe bet to document without wasting our time. Any earlier than that, and they may be cancelled due to lack of interest, or be so unstable that they will change significantly, meaning lots of rewriting (which we try to avoid where possible).

## Non-web standards technologies

Non-web standards technologies are technologies that do not follow our criteria summarized above. We would not normally consider them for documentation on MDN. However, there are many technologies that are not web standards, but are useful and interesting to web developers — think about developer tools, libraries, and frameworks as some of the more obvious examples.

Our mission statement is _"to provide developers with the information they need to easily build projects on the open Web"_. This suggests that we should consider documenting technologies that are useful to web developers, even if they are not open web standards, on the standards track, etc. Hence the creation of the Web-related technologies section as a place to house such documentation.

We want to maintain a certain level of quality on MDN, and not just open our doors to accept any documentation. To do so would make MDN Web Docs a messy place, and potentially harm the web industry by creation substandard, conflicting documentation.

Therefore, if you want to consider a non-web standard technology for inclusion in this section of MDN Web Docs, you should make sure that it matches the below criteria.

## The criteria

To be applicable for consideration, technologies should...

### Be open and not proprietary

At Mozilla we are supporters of open technologies, and don't wish to support closed technology ecosystems that are controlled by a single entity, not open for contributions by any interested party, and not interoperable across multiple platforms and systems. We believe that technology works better for humans when created out in the open.

### Be web-exposed in some way / related to web technologies

Our central remit is web standards technologies; there is no point starting to document technologies that do not relate to the web, or hold any interest to web developers.

### Show signs of interest and adoption

We don't want to waste our time and energy helping to document a technology that has no signals of interest and adoption from industry. It may just be that it is too early to start documenting the technology, and we could consider it in the future.

### Not be showing signs of being deprecated, or superseded

Related to the above point, we also don't want to waste our time helping to document something that is late in its lifecycle, and already showing signs of decline in interest.

### Not have an established documentation resource elsewhere

There are many libraries and frameworks in existence, which are not web standards, but are built on top of web technologies and very popular in the web industry. We do not document any of these because in general they all have established documentation resources already. It would be foolish to compete with the official resource of a popular framework — to do so would be a waste of time and probably end up confusing developers trying to learn the technology.

### Have a community willing to write and maintain the docs

The MDN Web Docs team concentrates on documenting the open web platform, and does not have time to spend on other documentation resources outside this remit. Therefore if you want a technology to be considered for documentation in this area of MDN Web Docs, you'll need to have a community assembled that is willing to write the documentation and maintain it after completion. Our team is happy to provide guidance in such cases, including edits and feedback, but we don't have time for much more than that.

## Next steps

If your chosen technology looks to meet the criteria, the next step is to propose it to the MDN team. See the [Process for selection](/en-US/docs/Related/Process_for_selection).

<!--content copied from /en-us/related/process_for_selection -->

## Process for selecting the new technology

If a technology looks like a good candidate for inclusion on the [Web-related technologies](/en-US/docs/Related) section of the site, the next stage is to contact us to discuss the technology, and propose why you think it should be included on MDN Web Docs. This article provides a list of what you should send to us in the proposal, along with how to send it over.

## Checklist

Non-web standards technologies will be considered for inclusion on MDN Web Docs on a case-by-case basis. For consideration, we need a short document describing:

- The technology, its core purpose/use cases, and target developer audience.
- What kind of industry/community buzz there is around the technology. For example:

  - Are lots of people using it? What is the industry adoption like?
  - Do lots of people want this information? Who?
  - What kind of target audience size is there for this information? Supporting statistics would help, if you have them.

- How the technology relates to core web technology and web browsers. Useful details are things like:

  - Does it use HTML and CSS, but generally not output to the web?
  - Is it supported in web browsers via a polyfill?

- What documentation/resources there are available already that cover the technology.
- How much documentation would need to be added to MDN:

  - List the expected number of guides, tutorials, reference pages for elements/methods/attributes, etc.
  - Provide a high level table of contents.
  - Mention the kind of "advanced" features you think you might need for this resource, beyond basic documentation pages. Are you expecting to include embedded videos, interactive code samples, etc.?

- Details on who will be writing the documentation. Who are these people, and why are they suited to the job?

You don't need to provide us with hundreds of pages of detail at this stage (in fact, we'd prefer it if you didn't). A couple of paragraphs on each of the above points is more than adequate. We are OK to accept any format as long as it is common and easy to send over the web. Text files, documents or slides are recommended.

## Submission and next steps

- After you've compiled the above document, send it to us over e-mail at <mdn-admins@mozilla.org>.
- After we receive this, we will consider the technology, then e-mail you back with one of the following answers:

  - **No**: We don't think this fits MDN Web Docs.
  - **Maybe**: We are not sure if this fits MDN Web Docs, and would like to ask some further questions.
  - **Yes**: We think this fits MDN Web Docs.

- If the response was maybe/yes, we will request a conversation (e.g. video, telephone, or email) with one or more representatives of the community interested in adding the documentation.
- If we still feel positive after the initial conversation, then we are good to go, and a member of our team will assist you in getting started with the documentation.

## See also

[Project guidelines](/en-US/docs/Related/Project_guidelines) — what you need to know to create a successful documentation project once your idea has been accepted onto MDN Web Docs.

<!--content copied from /en-us/related/project_guidelines -->
## Project guidelines for documenting the new technology

If you've had your chosen technology accepted for documentation on MDN Web Docs, the next step is to get started. This article provides you with all you need to know to get started on documenting your project.

## What does a successful project need?

A successful documentation project requires a number of things. We'll look at each of these in turn:

- A dedicated team
- A Project plan/roadmap
- Guidelines and standards
- An intuitive structure
- Maintenance

## Dedicated team

Make sure you have a dedicated team in place that will be there both to write the documentation in the first place, and maintain it after the major bulk of the work is completed and updates are required.

Have a think about how much work there is to do on your particular docs project, and how many people you might need for that.

If it is a large project, you might benefit from having a few writers, a technical reviewer to check that the work is correct, a copy editor to clean up the language, someone to write code examples, etc.

On a smaller project, you might have one or two people taking on multiple roles. Whatever you want to do is fine, as long as it works for you. You will be assigned a member of MDN staff to provide guidance on the MDN Web Docs side of things, and advice and help in general.

You should assign one (or two) team leads, to act as a central point of contact for the MDN team member, and anyone else wishing to contact the team about it (you might get more offers of help, for example).

Once your team is assembled, you'll need to get them all to [create MDN accounts](/en-US/docs/MDN/Contribute/Howto/Create_an_MDN_account), and then talk to your MDN rep to work out what site permissions each person needs (e.g. creating pages, moving pages, etc.)

## Project plan/roadmap

Write down a plan for the work — what needs to be done, and when? What milestones do you need to reach so that progress is healthy? If the project is large, you should consider getting one of your team members to be a project manager for the project, and using a project tracking tool like [Trello](https://trello.com/). You should also consider writing a sub-project plan for an initial release that encompasses the minimum set of documentation that is useful to publish (a _minimum viable product_), do that first, and then follow up with further additions later.

If the documentation resource is small, then this probably isn't so critical, but you still need to keep a record of what has been done and what hasn't, what stage each part of the documentation is at (e.g. not started, in progress, draft written, reviewed, done...), and who is working on what.

## Guidelines and standards

There are [guidelines available on MDN](/en-US/docs/MDN/Guidelines) that state how we expect documents to be written, and how to use the tools on the site to create them.

Since this is a project in its own right, you may have additional guidelines on language or code styles that you expect to be followed. Feel free to keep a record of these, and even host them on a page inside your own project pages.

In terms of standards, you are expected to maintain a reasonable level of quality for your documentation to stay on MDN. Your MDN rep will work with you on this to make you clear on what is expected. It is a good idea to produce a prototype showing what each type of page in your documentation should look like (e.g. an element or method reference page, a code example...) so that people have a template to follow.

> **Note:** MDN is primarily an English site (en-US). The primary language for your resource should be in US English. If this really doesn't make sense for your project (e.g. it might be for a tool usable in a specific non-English locale), then talk to us about it, and we'll see how we can accommodate this.

## Intuitive structure

If you went through the submission process then you should already have a rough plan of what you are going to write for your documentation resource. At this point you should refine that into a site structure plan — think about what the document hierarchy will be, and where everything will fit and link together.

Each project will be different, but we'd roughly recommend something like this:

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

### Page templates

Each page type that you will use in your project should have a page template for others to copy the structure from. You should decide on these early on.

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

### Project metadata

By project metadata, we mean things like:

- Team contact details, if you'd rather put them on a separate page.
- Project-specific language or code guidelines.
- Code templates to write new examples into.
- Reusable asset lists.

## Maintenance

The documentation will need to be maintained to remain on MDN:

- MDN is a Wiki; when others make changes to the docs, a core community member for that technology needs to review those changes to make sure the content is still good. This can be done via MDN's ["Watch" functionality](/en-US/docs/MDN/Contribute/Tools/Page_watching).
- When changes occur to the technology that require documentation updates, the community needs to make updates as appropriate, keeping the same standards and process in mind as the original documentation.

## Archiving documentation

If the documentation appears to be:

- Stale/unmaintained
- Stalled without being finished
- Low quality
- Becoming obsolete

If positive changes are not observed over a period of 6 months, it will be considered dead documentation, and will be archived. If you are having trouble with meeting the requirements for a successful documentation project, please reach out to your MDN rep and discuss it. We can try to work through the issues together if we know what they are; silence is never a solution.

We need to be strict on such matters — we can't let the site fill up with bad quality, incomplete, or obsolete documentation — it harms our reputation.