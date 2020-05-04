---
layout: post
title: "Changes in the Seventh Edition of JavaScript: The Definitive Guide"
excerpt_separator: <!--more-->
---

The seventh edition of my book, _JavaScript: The Definitive Guide_ is
scheduled for release less than a month from today. If you own the
sixth edition, it is very much time for an upgrade. This post explains
what has changed in this new edition.

- Most importantly, this edition is up-to-date and covers the very
  newest ES2020 features like `?.` and `??`. The sixth edition covered
  ES5, which means that I have added documentation of all the language
  features of ES6, ES2016, ES2017, ES2018, ES2019 and ES2020 for this
  update.

- The first thing you'll notice when you see the new edition
  <!--more--> is that O'Reilly has [changed the
  cover](/2020/04/27/jstdg7-cover-image.html). The old cover style
  still seems iconic to me, but this new style does seem like a nice
  modernization of the O'Reilly brand.

- The second thing you'll notice when you pick the book up is that it
  is significantly thinner. The 6th edition was a 1096 page brick; the
  7th edition is about 400 pages slimmer: still a substantial book,
  but not absurdly so. The main reason for this reduced page count is
  that I've removed the reference section. In 2020 it is faster to
  look reference information up on
  [MDN](https://developer.mozilla.org) than it is to flip through a
  printed book. It simply doesn't make sense to include that material
  in this new edition.

- The cover of the 6th edition includes the tagline _Activate Your Web
  Pages_. I don't remember when that was added, but it feels very
  dated (like, "DHTML"-level dated) to me. For the 7th edition I asked
  O'Reilly to change this to _Master the World's Most-Used Programming
  Language_ and the new cover positions this as a subtitle. (The
  "most-used" claim is from the [2019 Stack Overflow developer
  survey](https://insights.stackoverflow.com/survey/2019#technology)
  which found "For the seventh year in a row, JavaScript is the most
  commonly used programming language".)

- "Master the world's most-used programming language" isn't just
  marketing copy for the cover, though. It reflects a real change in
  focus for the book. The web platform has become way too large to be
  documented _definitively_ by any one book. And, with the rise of
  Node, JavaScript isn't just the language of web browsers anymore. So
  starting with this seventh edition I will be documenting the
  JavaScript language definitively, and providing an in-depth (but not
  definitive) introduction to the use of that language with Web APIs
  and Node APIs.

  The 6th edition devoted about 290 pages to the language itself, 410
  pages to the Web platform, and a meager 10 pages to Node. The 7th
  edition has 400 pages on the language, 160 pages on the Web, 60
  pages on Node, and 30 pages on the JavaScript ecosystem of tools and
  language extensions. The cuts to the web documentation are not as
  deep as they seem, however. Much of the reduction in page count was
  achieved by removing material that is no longer relevant in 2020,
  such as coverage of `document.write()`, `attachEvent()`, and
  pretty much all mentions of Internet Explorer. There was a lot of
  material on CSS that I've removed, and the entire chapter on jQuery
  is gone (it is still available as [a pocket
  reference](https://amzn.to/2Yvae17) though).

- The 7th edition has a number of rewritten and new chapters:

  - Chapter 6, _Objects_, and Chapter 8, _Functions_, are not
    completely rewritten but they include a lot of new material
    covering all the ES6 extensions to object literal syntax, arrow
    functions, parameter defaults, rest parameters, the spread
    operator, and so on.

  - Chapter 9, _Classes_, is entirely rewritten. The chapter begins
    the old fashioned way: it demonstrates how to create a JavaScript
    class by directly defining methods on the prototype object.  I
    believe that it is still important to understand how classes
    actually work in JavaScript. But after some initial examples of
    this technique, the chapter switches to using the modern `class`
    keyword.

  - Chapter 10, _Modules_, is new. When I wrote the 6th edition,
    JavaScript had no module system and my discussion of using
    immediately-invoked function expressions as modules was simply
    tacked on to the end of the classes chapters. This new chapter
    documents both the module system used by Node and the ES6-standard
    modules that are now (finally!) supported by all browsers.

  - Chapter 11, _The JavaScript Standard Library_, is a new chapter
    that covers maps, sets, typed arrays, dates, errors, JSON, and
    internationalization. The existing chapter on regular expressions
    from the 6th edition has been updated and turned into a (long)
    section of this chapter. This chapter also covers three APIs that
    are not formally part of the JavaScript language, but that are
    implemented by browsers and by Node: the console API, the URL
    class, and the `setTimeout()` and `setInterval()` functions.

  - Chapter 12, _Iterators and Generators_ is new, and documents
    exactly what the title says. This chapter teaches you how to use
    `Symbol.iterator` to make your own classes iterable so that they
    work with the `for/of` loop. And it also explains generator
    (defined with `function*`) and the `yield` and `yield*` keywords.

  - Chapter 13, _Asynchronous JavaScript_ is a detailed discussion of
    asynchronous APIs and explains how to use events, callbacks,
    Promises, and `async` and `await`. Promises are a revolutionary
    addition to JavaScript, but using them correctly can be hard
    unless you understand them thoroughly. This chapter goes deep in
    an attempt to definitively explain Promises.

  - Chapter 14, _Metaprogramming_ is a grab-bag of advanced language
    features that may be of primary interest to those writing
    libraries for use by other programmers. It explains property
    descriptors, object extensibility, template tag functions, proxy
    objects, the Reflect API and well-known symbols.

  - Chapter 15, _JavaScript in Web Browsers_ is by far the longest
    chapter in the book, introducing the Web platform in 160 pages. It
    includes the content from the 6th edition that is still relevant,
    plus new material covering web components, `fetch()`,
    `history.pushState()` and more. This chapter concludes with an
    extended example that implements a multi-threaded Mandelbrot set
    viewer app. The example demonstrates web workers (and includes a
    Promise-based WorkerPool utility class), inter-thread
    communication with `postMessage()`, the transfer (without copying)
    of array buffers between threads, history management with
    `pushState()` and `popstate()`, keyboard and pointer events,
    scripted CSS transforms, the URL() class, and generators.

  - Chapter 16, _Server-Side JavaScript with Node_, is a detailed
    introduction to Node that starts with the fundamentals: events,
    buffers, and streams. This is followed by practical sections on
    working with files, making HTTP requests, serving HTTP
    responses, and concurrent programming with threads and child
    processes.

  - Chapter 17, JavaScript Tools and Extensions, concludes the book
    with an introduction to some important parts of the JavaScript
    ecosystem: eslint, prettier, Jest, npm, code bundlers, Babel, JSX
    and Flow. I couldn't document everything, so this chapter is a
    curated—but not particularly opinionated—list of some of the most
    popular JavaScript tools and extensions. This chapter is intended
    not as a recommendation for particular tools and technologies, but
    as an exhibition of the kinds of tools that professional
    JavaScript programmers regularly use.

It is a really good book! You can [order it here](https://amzn.to/2yn1VK8).
