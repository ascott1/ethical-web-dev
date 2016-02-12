## Introduction to progressive enhancement

Progressive enhancement is a term that often insights intense debate. For many, progressive enhancement can be summed up as “make your site work without JavaScript.” While, developing a site that works without JavaScript often does fall under the web of progressive enhancement, it can define a much more nuanced experience.

In Aaron Gustafson’s seminal A List Apart Article, [Understanding Progressive Enhancement](http://alistapart.com/article/understandingprogressiveenhancement), he describes progressive enhancement as a peanut M&M. The peanut being the core experience, which is essential to the user. The chocolate encompasses the features and design that take us beyond the naked peanut experience and add some much loved flavor. Finally, the candy shell, though not necessarily needed, provides added features, such as not melting in your hand. Oftentimes this example is translated to HTML as the peanut, CSS as the chocolate and JavaScript as the candy shell.

In today’s web application landscape it may be over simplified to consider progressive enhancement as simply “works without JavaScript.” In fact, many of the rich interactions and immersive experiences that have come to define the modern web certainly require JavaScript. For progressive enhancement to be considered an ethical issue in web development, we must tie it back to user needs. Progressive enhancement is about defining what a user *needs* and ensuring that it is always delivered to them, in a way that will work regardless of network conditions, device, or browser.

I prefer [Jeremy Keith’s take](https://youtu.be/-yIbKaA3wCo) that progressive enhancement is a “process” rather than a specific technique or set of technologies. By Keith’s definition this process looks like:

1. Identify the core functionality
2. Make that functionality available using the simplest technology
3. Enhance!

As a developer it is our job to determine the “core functionality” of our application and what is an enhancement. This allows us to develop a baseline to build from, yet the baseline for any given project may be different.


In his 2012 article, [Stumbling on the Escalator](https://www.christianheilmann.com/2012/02/16/stumbling-on-the-escalator/), Christian Heilmann appropriated a Mitch Helberg comedy bit about escalators for progressive enhancement:

> An escalator can never break – it can only become stairs. You would never see an “Escalator Temporarily Out Of Order” sign, just “Escalator Temporarily Stairs. Sorry for the convenience. We apologize for the fact that you can still get up there.”

As a person who has spent a lot of time in the Washington DC metro system, I can really appreciate this analogy. Thankfully, when an escalator is out I am not trapped underground, but instead can huff up the now stairs to the street.

Oftentimes, when beginning a project, I am presented with a set of business requirements or a beautiful design. From these, it can be easy to see the end goal, but skip the baseline experience. If, in the case of the escalator, my requirement was to “build a transportation system that will allow Metro riders to travel from the terminal to the street,” my initial reaction may be to create an elevator. You can imagine how this might become problematic.

Developing web apps works in much the same way. If we only consider the end goal, we run the risk of leaving our users stranded. By focusing on and providing a solid baseline for our users, we set ourselves up for success in many other aspects of ethical web development, such as accessibility and performance.

## It's not no JS

Progressive enhancement isn't "making the whole thing work without JavaScript" or taking an "all or nothing" approach.

## Benefits of progressive enhancement

- Works if a resource fails to load
- Easier to archive and index
- Faster initial load times

## Defining the baseline experience

If progressive enhancement is the process of defining a baseline experience and building up from there, how do we define that initial baseline? The goal is to consider what the bare minimum is that a user requires to be able to user our application. Once we have defined this, we can layer on additional style and functionality. For some applications this may be a completely JavaScript free version of the experience, while for others it may be a less fully featured version, and still others it may be providing some server rendered content on the initial page load only.

The key is to not think of progressive enhancement not as an either/or option, but instead as a range, determining what is the best decision for users.

![GRAPHIC OF PROGRESSIVE ENHANCEMENT GRADIENT](IMG LINK)

I'd encourage you to take a few minutes and consider what the baseline experience might look like for a few different types of websites and applications. Identify the primary goal of the site and determine the minimum amount of technology needed to implement it. To take it a step further, write some markup or psuedo code explaining how you might implement those baseline features.

- News website
- Social network (write text posts and read the feed of friends)
- Image sharing website
- Web chat application
- Video chat application

When working on your own applications, I would encourage you to do the same. First, determine the baseline experience for your users and build the application from there. This programatic approach also pairs well with the [Agile](LINK) approach to software development, where the goal is to deliver working software at the end of each development sprint.


## Is progressive enhancement still relative?

Some may question how relative progressive enhancement is today, when [GET PERCENTAGE] of user's browse the web with JavaScript enabled. This puts the focus too heavily on progressive enhancement as a JavaScript free version of a site. In fact, some types of applications, such as video chat, absolutely require some form of JavaScript to work in the browser. The goal is to provide the absolute minimum for a working product and ensure that it is delivered to user's browser.

[PARAGRAPH ABOUT RURAL AND DEVELOPING AREAS WEB CONNECTIONS]

[PARAGRAPH ABOUT OPERA MINI]

For those of us in developed or urban areas, we most likely have experienced what [Jake Archibald]() has termed "Lie-Fi." This is a connection where our mobile device seems to think it is connected to wifi, but the signal strength is so weak that pages or sites are slow.

[SCREENSHOT OF Lie-Fi]

In 2014 the UK's Sky broadband accidentally briefly [blocked the jQuery CDN](http://www.thinkbroadband.com/news/6261-sky-parental-controls-break-jquery-website.html), presumably leaving many users perplexed with broken websites. If you choose to serve a library from a CDN, I would recommend following the [HTML5 Boilerplate's](https://html5boilerplate.com/) lead and provide a local fallback as well.

```html
<script src="https://code.jquery.com/jquery-1.12.0.min.js"></script>
<script>window.jQuery || document.write('<script src="js/vendor/jquery.min.js"><\/script>')</script>
```

## How do we do progressive enhancement today?

In the world of modern JavaScript driven web applications, there are still several practical approaches we can take to build progressively enhanced sites. These approaches can be very simple or leverage exciting web technology buzz words such as Isomorphic JavaScript or Progressive web applications. Since progressive enhancement is not a one sized fits all approach, you may want to evaluate this options and choose the one that best works for your project.

Let's take a look at a few of these options and how they may be used to build the best possible experience for a user.

Perhaps the simplest and most progressive is to completely avoid a JavaScript dependent first page render. By rendering all of the **necessary** content on the server, we can ensure that a user receives a useable page, even if only our HTML makes it to their browser. The key here is to focus on what is necessary. There may be additional JavaScript required functionality, but if it isn't necessary we can allow it to quietly fail in the background or present the user with different content.

[auto loan calculator example?]

Render landing/home page as HTML while async load JS

Another option, or one that may paired with the previous, is to sniff out outdated browsers and avoid serving JavaScript to those browsers. We can continue to serve our core content and functionality to those browsers (it was progressively enhanced after all!), but offer a significantly simpler experience.

To sniff out older browsers, we can use a technique demonstrated by Jake Archibald from [his talk](https://youtu.be/EVEiIlJSx_Y) at Nordic.js in 2015:

```javascript
(function() {
  if (!('visibilityState' in document)) {
    return false;
  }

  // rest of your code
}());
```


You may be thinking, "but I want to build *modern* web applications and these are old techniquest!" Certainly these techniques feel out of sync with the approaches of some of the popular JavaScript frameworks, but recently we've seen the most popular web application approaches trend back towards a progressive enhancement model.

Isomorphic or Universal JavaScript is a technique that allows the a developer to pair server and client side JavaScript into a "write once, run everywhere approach." This technique means that the initial application will render on the server,  using Node.JS and then run in the browser.

<ASIDE>
Though my description may be over simplified, Isomorphic JavaScript is an exciting approach for developers and teams who are using server side JavaScript. To learn more about Isomorphic JavaScript, I recommend taking a look at these resources:

- [LIST OF RESOURCES]
</ASIDE>

If a fully Isomorphic JavaScript approach is overkill for an application, Henrik Joreteg has coined the term ["Lazymorphic" applications](https://blog.andyet.com/2015/05/18/lazymorphic-apps-bringing-back-static-web/). A Lazymorphic app is simply one where the developer we simply pre-renders as much of the application as possible as static files at build-time. Using this approach we can choose what we rendeder, making something useful for the user while withholding JavaScript depndent features.

Lastly, the term Progressive web apps has recently taken hold. Rather than specific technology, this term has come to encompass several inter-related techniques for web development.

## In summary

## Quick tips

- Focus on user needs.
- Define a baseline experience and build from there.
- Remember that your site doesn’t have to look the same in every device and browser.
- Avoid the assumption that all assets will be available.
