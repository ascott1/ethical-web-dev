# URL Design

The humble hyperlink one of the most powerful aspects of the web. This ability to connect to any resource on the web with through a URL is what makes the everywhere web possible. As developers we should aim to expose permanent, human readable, deep links to our users.

In 1996 the creator of the web, Tim Berners-Lee, drafted [Universal Resource Identifiers -- Axioms of Web Architecture](https://www.w3.org/DesignIssues/Axioms.html). This document consists of several axioms of URL design, many technical in nature, but the first (and arguably most important) is “universality.” By Berners-Lee’s definition, “any resource anywhere can be given a URI” and “any resource of significance *should* be given a URI” (emphasis mine). By conforming to these expectations of the web we make it easier for our users to share and interact with the web. 

## Permanence

> What makes a cool URI?
> A cool URI is one which does not change.
> What sorts of URI change?
> *URIs don't change: people change them.*

— [THE W3C](https://www.w3.org/Provider/Style/URI.html)

One of the beautiful things about developing for the web is the ability to evolve our applications over time, immediately deploying updates to every user. With this ability, however, we often introduce states of fluctuation as we change server configurations, undergo content redesigns, and adapt to new technologies and frameworks. In the paper [Perma: Scoping and Addressing the Problem of Link and Reference Rot in Legal Citations](http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2329161) the authors point out that “more than 70% of the URLs within the Harvard Law Review and other journals, and 50% of the URLs found within United States Supreme Court opinions, do not link to the originally cited information.” This is often referred to as “link rot,” where once valid URLs no longer return the originally linked resource. The prevalence of link rot is something that online archiving tools such as the Internet Archive’s [Wayback Machine](https://archive.org/web/) and [permalink.cc](https://perma.cc/) attempt to combat. For his part, Tim Berners-Lee has wrote about the idea of [persistent domains](https://www.w3.org/DesignIssues/PersistentDomains) 16 years ago, but this idea has, thus far, failed to become a reality.

As developers, we should avoid arbitrarily changing URLs for our applications as much as possible. If significant changes to content require a URL change, we should always forward the previous URL to the new page. When creating permanent URLs the first step is to ensure that technology does not dictate the URL. Often sites display language filetypes at the end of a URL such as `.php` or `.asp`.  This doesn’t accommodate for future iterations of an application that may be built upon a different technology stack. By remaining technology independent in URL design we take the first step towards more permanent URLs.

The importance or persistent URLs is that they help to preserve the web. When URLs persist, outside links remain active, user bookmarks remain relevant, and information remains consistent. By focusing on good URL design we can help to ensure the permanence of URLs across the web.

## Shareable URLs

Commenting on an early draft of the [Principles for Ethical Web Development](https://ethicalweb.org/), [Dean Marano](https://github.com/deanmarano) raised the important issue of creating shareable URLs.

> One thing that for me is very important when building apps is the ability to share a URL - either with myself or with others - easily. By leveraging this built in feature of the web, it makes it much easier to share, bookmark, and be a good web citizen.

This ability to link and share is a key advantage that web development has over other forms of application development. A few ways that we can aid this practice in our applications, is to give our users the ability to link out to content that is within our applications, without requiring a login when possible, ensuring that URLs are updated when doing client-side routing, and by avoiding non-standard URL formats such as hash-bang URLs (`http://example.com/#!/foo/`).

## URL Design

Simply Providing URLs is the first step, but as Jakob Nielsen has described them [URLs are a form of user interface](https://css-tricks.com/guidelines-for-uri-design/). Even in the era of search engines, a [study from Microsoft Research](http://research.microsoft.com/apps/pubs/default.aspx?id=70395) to determine if URLs were observed by average users revealed that users spent 24% of their gaze time looking at the URLs in search results. With this in mind, how can we design URLs that are effective and usable?

### Keep URLs simple

Effective URLs are simple, short, and human-friendly. This makes them easier to type and remember for users.

WordPress is the most popular content manager for the web and powers over 25%[^1] percent of websites. Unfortunately, until relatively recently[^2], the default WordPress [permalink structure](https://codex.wordpress.org/Introduction_to_Blogging#Pretty_Permalinks) produced URLs such as:

```
/index.php?p=423
```


To a user this URL format is seemingly random and arbitrary. Fortunately, WordPress allowed users to create “pretty” permalink structure, and as of 2015, now does this by default. The pretty permalink structure can be descriptive and clean, such as:

```
/posts/effective-altruism/
```

WordPress core contributor Eric Lewis [reportedly commented on the change](https://wptavern.com/wordpress-4-2-will-automatically-enable-pretty-permalinks-for-new-sites-on-installation) saying that “Delivering pretty permalinks by default seems in line with a bunch of core philosophies – great out-of-the-box, design for the majority, simplicity, clean, lean and mean.” I agree with Eric, this is a great change, beneficial to users across the web, and a great example of how much more legible a well designed link can be.

By creating link structures that are simple and human readable, we are able to provide our users with a clear description of a URLs content.

[^1]: https://w3techs.com/technologies/history_overview/content_management/all/y
[^2]:https://core.trac.wordpress.org/changeset/31089

### Make URLs Meaningful and Consistent

URLs should be both meaningful and consistent throughout a site. Meaningful URLs clearly represent a resource and accurately describe its contents with the title and, when useful, keywords. A website that holds a blog may put blog posts within a `/blog/` URL structure such as `/blog/url-design` and `/blog/ethical-web`. These URLs make the intent of the resource clear and are understandable to the user. URLs should also be consistent, using recognizable patterns. If when logged into an application my profile’s URL is `https://example.com/user/adamscott`, I would expect to find another user’s profile with the same URL structure of `/user/username`.

### Make URLs “Hackable”

URLs should be “hackable” up the tree of the URL in a way that allows users to visualize the site structure. For example, if a URL is `https://example.com/artist/albums/album-name/` changing the URL to `https://example.com/artist/albums/` would return a page displaying the artist’s albums and `https://example.com/artist/` an artist page. Doing this makes our URLs more meaningful and predictable for our users, while allowing them to navigate down the tree and share URLs through only the logical URL structure.

As [Peter Bryant](http://blog.2partsmagic.com/restful-uri-design/) describes this:

>  If your URLs are meaningful they may also be predictable. If your users understand them and can predict what a url for a given resource is then may be able to go ‘straight there’ without having to find a hyperlink on a page.

By providing users with a hackable URL tree, we enable them to have an immediate understanding of how our site structure works.

### API URL Design

Often, when designing URLs we are not limited to designing them for end-users. APIs provide a URL interface for both internal and external developers when interacting with our services. To make our API URLs more user friendly we can aim to focus on URL permanence and comprehension.

Much like HTML URLs, when design API URLs we should focus on permanence. As technology and services change, it is likely that our API will evolve. When exposing a public API, it is common practice to host our API on a subdomain named, API. This allows us to run our API in its own environment while tying it to our top level domain.

```
https://api.example.com
```

Perhaps one of the most important things we can do for permanence is to always include an API version in the URL. This allows us to adopt changes to our application’s technology and features while continuing to return results for past versions of the API.

```
https://api.example.com/v1/
```

Use nouns to identify resources. This describes what the resource returns rather than what they do. This means that we should favor identifiers such as `users` over verb-driven identifiers like `getUsers` or `list-users`.

```
https://api.example.com/v1/users/
```

Similar to page URLs, APIs should work up and down the URL tree, making them “hackable.” If `/users/` returns a list of users `/users/username` should return the results for a specific username.

```
https://api.example.com/v1/users/
https://api.example.com/v1/users/psinger/
```

Lastly, our API should filter advanced results by query parameters. This allows us to keep the base of our URLs reasonably simple and clean while allowing for advanced filters and sorting requirements.

```
/users/psinger/friends?sort=date
```

As API developers, the URL is our interface. By considering their permanence the design URLs we are building more useful and sustainable APIs.

—

Through purposeful design of  our URLs, we can create URLs for our applications that are both easy to navigate and share by our users. Focusing on URL permanence, simplicity, and predictability aids in building an everywhere web that simplifies access for everyone.

## Further Reading

- [Tim Berners-Lee’s Axioms](https://www.w3.org/DesignIssues/Axioms.html)
- [Persistent Domains - Strawman ideas on Web Architecture](https://www.w3.org/DesignIssues/PersistentDomains.html)
- [Guidelines for URI Design](https://css-tricks.com/guidelines-for-uri-design/)
- [Lessons from a 40 Year Old](http://a.wholelottanothing.org/2012/03/my-webstock-talk.html)
- [URL as UI](https://www.nngroup.com/articles/url-as-ui/)
- [REST-ful URI Design](http://blog.2partsmagic.com/restful-uri-design/)
- [Best Practices for Designing a Pragmatic RESTful API](http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)
