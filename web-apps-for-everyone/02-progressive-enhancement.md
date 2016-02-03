## Introduction to progressive enhancement

Progressive enhancement is a term that often insights intense debate. For many, progressive enhancement can be summed up as "make your site work without JavaScript." While, developing a site that works without JavaScript often does fall under the web of progressive enhancement, it can define a much more nuanced experience.

In Aaron Gustafson's seminal A List Apart Article, [INSERT TITLE], he describes progressive enhancement as a peanut M&M. The peanut being the core experience, which is essential to the user. The chocolate are the features and design that take us beyond the naked peanut experience and add some much loved flavor. Finally, the candy shell, though not needed provides added features, such as not melting in your hand. Oftentimes this example is translated to HTML as the peanut, CSS as the chocolate and JavaScript as the candy shell. In today's web application landscape this may be over simplified.

For progressive enhancement to be considered an ethical issue in web development, we must tie it back to user needs. Progressive enhancement is about defining what a user *needs* and ensuring that it is always delivered to them. In this way, I prefer Jeremy Keith's take that "progressive enhancement is a process" [check quote/source and expand](https://www.youtube.com/watch?v=-yIbKaA3wCo).

How does the process of progressive enhancement work? As a developer it is our job to determine what is a "core functionality" of our application and what is an enhancement. This allows us to develop a baseline to build from, yet the baseline for any given project may be different.

In his [INSERT YEAR] article, [INSERT NAME] appropriated a Mitch Hedberg comedy bit about escalators for progressive enhancement. When an escalator breaks, it becomes stairs. As a person who has spent a lot of time in the Washington DC metro system, I can really appreciate this analogy. Thankfully, when an escalator is out I am not trapped underground, but instead can huff up the now stairs to the street.

Oftentimes, when beginning a project, I am presented with a set of business requirements or a shiny design. From these, it can be easy to see the end goal, but skip the baseline experience. If my requirement was to "build a transportation system that will allow Metro riders to travel from the terminal to the street," my initial thought may be to create an elevator. You can imagine how this might become problematic.

Developing web apps works in much the same way. If we only consider the end goal, we may leave our users stranded.

Progressive enhancement isn't "making the whole thing work without JavaScript" or taking an "all or nothing" approach.

## Defining the baseline experience

Provide a short "workbook" style space for considering what the baseline experience might be for a selection of common application types.

- Social network (post/read feed)
- Image sharing website
- Chat
- Video

## Benefits of progressive enhancement

- Works if a resource fails to load
- Easier to archive and index
- Faster initial load times

## Is progressive enhancement still relative?

Some things will require JS (Vide0 - talky.io, Google Hangouts)

"Lie-Fi" (term coined by Jake Archibald for weak wifi signal)

Sky broadband [blocked the jQuery CDN](http://www.thinkbroadband.com/news/6261-sky-parental-controls-break-jquery-website.html)

## How do we do progressive enhancement today?

Nothing should have a JS dependent first render.

Sniff out a modern browser (Jake Archibald's example https://www.youtube.com/watch?v=EVEiIlJSx_Y) and don't serve JavaScript to those browsers. Only if you need to support old browsers

Render landing/home page as HTML while async load JS

Isomorphic/Universal JS/Ember Fastboot
Lazymorphic JS
Progressive web apps

## Quick tips

- Define a baseline experience and build from there.
- Your site doesn’t have to look the same in every device and browser.
- Try not to assume that all assets will be available.
