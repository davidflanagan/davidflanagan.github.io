---
layout: post
title: "JavaScript Features To Forget"
excerpt_separator: <!--more-->
---

The first demo of the language that was to become JavaScript took
place [almost exactly 25 years
ago](https://twitter.com/BrendanEich/status/1259403604626038784).

The language was released, as LiveScirpt, in a beta of
Netscape Navigator in the fall of 1995, and renamed to JavaScript
later that year. Sometime late that year I began work on the first
edition (O'Reilly published it as the "beta edition") of _JavaScript:
The Definitive Guide_, and it was published in August of 1996, meaning
that it is going on 24 years old now.

With the [seventh edition](https://amzn.to/3dFeqjf) coming out in just
a few weeks, I want to take a trip down memory lane and blog about
some old weird features of JavaScript and of the early web platform
that we can now, mercifully, forget about.
<!--more-->
One of the reasons that the
new 7th edition is thinner than the 6th edition is that I've [removed
the reference
section](/2020/05/03/changes-in-the-seventh-edition.html). But in
addition, I found that there was a lot of stuff that was simply no
longer relevant to web developers in 2020. Web compatibility is
forever (or for at least more than 25 years) so browser vendors may
need to keep supporting old and obscure language and platform features
for a long time to come. But there is no need for the rest of us to
clutter our minds with them anymore.

So here are some JavaScript and Web platform features that no longer
bulk up the page count of _JavaScript: The Definitive Guide_. I'm
happy to say goodbye to them. (I feel myself winding up for a bit of a
rant here, so be warned that this is not carefully researched; just my
memories of how things were in the bad old days):

- The `arguments` object has been completely obviated by the
  introduction of `...args` in ES6. It was always difficult to explain
  the weird way it interacted with named arguments and to always
  caution about its performance implications. You may still see it in
  legacy code and you may be reminded of its presence if you try to
  name a local variable or function parameter `arguments` in strict
  mode, but now that we have rest arguments, it should be allowed to
  slink into oblivion.

- We used to have to worry about the performance of repeated string
  concatenation. There was a period of where we all learned to push
  strings onto an array, and then use `join()` to concatenate
  everything at the end. Then JavaScript got fast and we were all
  "Well, actually" and unlearned that pattern. And now with template
  literals, who even uses string concatenation anymore!

- `document.write()` was pretty much the main feature of JavaScript
  at the very beginning, before the DOM. (If you did not use
  JavaScript in the 20th century, you may not know that there was a
  time before the DOM, but it is true. There was a property you could
  set to change the background color of a web page, but no way to
  actually alter the document tree once the document had been
  parsed.) IIRC you could even insert scripts into a document with
  `document.write()`, but you had to be careful to break the closing
  `</script>` tag into two strings so that the HTML parser wouldn't
  interpret it as the end of the currently-running script.

- HTML didn't have an `<iframe>` in the early days, but there was
  `<frameset>` and `<frame>`. The `window.frames` property was an
  array of the nested window objects that represented the frames in a
  document. It was possible to actually call the `open()` method of a
  document in a frame, and then use `document.write()` to dynamically
  generate an entire document inside that frame. That was kind of
  cool, actually. Because frames could be nested inside other frames,
  every Window object had a `frames` array that contained its children
  frames, and a `parent` property that referred to the containing
  window, and a `top` property that referred to the toplevel
  window. Earlier editions of my book dedicated long sections and
  complicated figures to explaining all of this.

- There are all kinds of obsolete techniques for referring to
  particular elements within a document. The `frames` array was one,
  but, IIRC, there were also `links` and `images` arrays as well that
  were literally just a list of all the links and images in a
  document. IE (version 4, I think) went all-in and introduced
  `document.all`: an array of all elements in the document. (This was
  the beginning of the DOM and of "DHTML"—kind of like the first fish
  that crawled onto dry land.) `document.all` had all kinds of weird
  features: it was an array that also had methods for looking up
  elements by name or something like that. `document.all` was never
  standardized, but even the standard methods like
  `document.getElementById()`, `document.getElementsByName()`,
  `document.getElementsByTagName()` and
  `document.getElementsByClassName()` seem obsolete today, crushed
  into irrelevance by jQuery's `$()` function and the standard
  `document.querySelector()` and `document.querySelectorAll()` methods
  that it inspired. Through the power of CSS selectors those two
  functions obsolete everything that came before.

- The thing I hated most about Internet Explorer was that it used an
  `attachEvent()` method for registering event handlers. In my memory,
  they did this even though the standard `addEventListener()` had
  already been defined, and that really annoyed me. Events and event
  handling were one of the biggest sources of incompatibility on the
  web, and for years JavaScript programmers (and JavaScript book
  authors) had to deal with a lengthy list of differences between the
  IE event model and the standard event model. Event handling code
  had to be written twice: once for IE and once for Firefox. Book
  chapters about events were twice as long as they needed to be
  because there were two similar, but completely incompatible ways of
  dealing with them. One of the major features of jQuery was that it
  implemented its own event compatibility layer so you only had to
  know about jQuery events, and I suspect that this was an important
  reason for its popularity.

- The original DOM API was defined during the era of magical thinking
  about XML. (People really seemed to believe for a couple of years
  that XML was going to solve all data problems. It was a strange
  time.) Somehow the W3C committed that defined the DOM API got
  infiltrated by Java people who felt it was appropriate to define a
  single API to be used by JavaScript programmers working with HTML
  documents and Java programmers working with XML data. That's why we
  have weird things like Attr nodes (which are best ignored). One of
  the things that always bugged me about the DOM Level 3 API was that
  to remove an element `e` from the document, you couldn't just write
  `e.remove()` as we would today. You actually had to write
  `e.parentNode.removeChild(e)`.

Anyway, it is 2020 now and I promise that [the new 7th edition of my
book](https://amzn.to/3dFeqjf) will not subject you to lengthy
explanations of any of those old features that are best left
forgotten.
