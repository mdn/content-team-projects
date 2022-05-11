[MDN Web Docs](https://developer.mozilla.org) is a complex project with lots of moving parts. It's a good idea to get familiar with the projects different repositories, as there is quite a few bits of the content that aren’t stored in the page sources and instead come from somewhere else.

This article acts as a quick guide to finding the different repositories (repos) you need to edit to update the different parts of MDN Web Docs content.

## Core repos

- **Core content**: <https://github.com/mdn/content>. The most important repo for MDN Web Docs content — this is where all the core English content of the site is stored, and where you'll make all standard changes to page content.
- **MDN Web Docs Platform**: <https://github.com/mdn/yari>. This is where the MDN Web Docs platform is stored, and where you'll go if you want to make changes to our high level page structure or rendering machinery.
- **Browser compatibility data**: <https://github.com/mdn/browser-compat-data>. This is where the data used to generate the browser compatibility tables found on our reference pages is stored ([example](/en-US/docs/Web/HTML/Element/progress#browser_compatibility)). Go here to make compatibility data changes!
- **Interactive examples**: <https://github.com/mdn/interactive-examples>. This repo stores the example code blocks that are found at the top of many of our reference pages ([example](/en-US/docs/Web/JavaScript/Reference/Global_Objects/globalThis)). Edit those examples here.
- **Bob** aka Builder of Bits: <https://github.com/mdn/bob>
  This repo stores the rendering code that produce the nice editable, copyable examples found at the top of many of our reference pages ([example](/en-US/docs/Web/JavaScript/Reference/Global_Objects/globalThis)).
- **Workflows**: <https://github.com/mdn/workflows>
  A growing collection of reusable GitHub Actions for use on MDN Web Docs repositories.
- **Translated content**: <https://github.com/mdn/translated-content>. This is where localized content lives. Go here if you want to help translate pages into any of our [actively maintained locales](https://github.com/mdn/translated-content#locales).

## Other repos

<!-- UPDATE WITH REPO TRIAGE -->

The MDN Web Docs GitHub org contains a huge number of example repos. These generally contain free-standing code examples that are often linked to from our pages, but occasionally you’ll find one of these examples embedded into a page using a macro call like this — `{{EmbedGHLiveSample("css-examples/learn/tasks/grid/grid1.html", '100%', 700)}}`.

Always remember, if you are updating the code on any given page, you'll need to update the corresponding example repo as well.

- **css-examples** [css-examples](https://github.com/mdn/css-examples) ...
- **js-examples** [js-examples](https://github.com/mdn/js-examples) ...
- **html-examples** [html-examples](https://github.com/mdn/html-examples) ...
- **web-audio-examples** [webaudio-examples](https://github.com/mdn/webaudio-examples).
- **web-component-examples** [css-examples](https://github.com/mdn/js-examples) ...



