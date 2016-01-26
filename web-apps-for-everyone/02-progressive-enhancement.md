## Introduction to progressive enhancement

## What is progressive enhancement?

2003 term coined on web monkey

Progressive enhancement is a process
https://www.youtube.com/watch?v=-yIbKaA3wCo

What is "core functionality" and what is an enhancement?

How does progressive enhancement differ from graceful degredation?

About building up from a baseline. That baseline will be different for each site.

Progressive enhancement is not just "this works without JavaScript."

Progressive enhancement isn't "making the whole thing work without JavaScript" or "all or nothing".

Progressive enhancement is about the user. What does the user *need*?

Try not to assume that all assets will be available.

Aaron Gustafson's peanut M&M example

your site doesn’t have to look the same in every device and browser

"You measure twice, and cut once"

## Benefits of progressive enhancement

- Works if a resource fails to load
- Easier to archive and index
- Faster initial load times


## Examples of progressive enhancement fails

- Sky broadband [blocked the jQuery CDN](http://www.thinkbroadband.com/news/6261-sky-parental-controls-break-jquery-website.html)



## Is progressive enhancement still relative?

Some things will require JS (Vide0 - talky.io, Google Hangouts)

"Lie-Fi" (term coined by Jake Archibald for weak wifi signal)

## How do we do progressive enhancement today?

Nothing should have a JS dependent first render.

Sniff out a modern browser (Jake Archibald's example https://www.youtube.com/watch?v=EVEiIlJSx_Y) and don't serve JavaScript to those browsers. Only if you need to support old browsers

Render landing/home page as HTML while async load JS

Isomorphic/Universal JS/Ember Fastboot
Lazymorphic JS
Progressive web apps
