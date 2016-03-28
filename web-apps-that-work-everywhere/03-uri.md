# URIs

> What makes a cool URI?
> A cool URI is one which does not change.
> What sorts of URI change?
> *URIs don't change: people change them.*

— [THE W3C](https://www.w3.org/Provider/Style/URI.html)

Expose permanent, human readable, deep links

Introduction - emphasize *permanence*, discuss the power of the humble link



> For site/web app development, longevity in your project means a lot of root changes to your site development. "Cool URIs don't change" is a good mantra to have, and there are several things you can do in your development to ensure longevity:

> - Permanent, human-readable clean URLs. They should never change, never expose the technology behind them.
> - Everything should degrade gracefully, even MetaFilter’s thread URLs can be cut off in email and still work.
> - Be platform agnostic and flexible. We run windows & linux servers, both physical and in the cloud. We run perl and coldfusion. By design, our URLs don’t reflect that. 

— Matt Haughey
    
    
> One thing that for me is very important when building apps is the ability to share a URL - either with myself or with others - easily. By leveraging this built in feature of the web, it makes it much easier to share, bookmark, and be a good web citizen.

— @deanmarano


## Principles of Good URI Design

- Represent an object, uniquely and permanently
- Be as human-friendly as possible
- Be consistent
- Be “hackable”
- Include keywords

Adapted from [Guidelines for URI Design](https://css-tricks.com/guidelines-for-uri-design/) by Jacob Gillespie

- Short (as possible). This makes them easy to write down or spell or remember.
- Hackable ‘up the tree’. The user should be able to remove the leaf path and get an expected page back. e.g. http://example.com/cars/alfa-romeos/gt you could remove the gt bit and expect to get back all the alfa-romeos.
- Meaningful. Describes the resource. I should have a hint at the type of resource I am looking at (a blog post, or a conversation). Ideally I would have a clue about the actual content of the URI (e.g. a uri like uri-design-essay)
- Predictable. Human-guessable. If your URLs are meaningful they may also be predictable. If your users understand them and can predict what a url for a given resource is then may be able to go ‘straight there’ without having to find a hyperlink on a page. If your URIs are predictable, then your developers will argue less over what should be used for new resource types.
Help visualize the site structure. This helps make them more ‘predictable’.
- Readable.
- Nouns, not verbs.
- Query args (everything after the ?) are used on querying/searching resources (exclusively). They contain data the affects the query.
- Consistent. If you use extensions, do not use .html in one location and .htm in another. Consistent patterns make URIs more predictable.
- Stateless.
- Return a representation (e.g. XML or json) based on the request headers, like Accept and Accept-Language rather than a change in the URI.
- Tied to a resource. Permanent. The URI will continue to work while the resource exists, and despite the resource potentially changing over time.
- Report canonical URIs. If you have two different URIs for the same resource, ensure you put the canonical URL in the response.
- Follows the digging-deeper-path-and-backspace convention. URI path can be used like a backspace.
- Uses name1=value1;name2=value2 (aka matrix parameters) when filtering collections of resources.

Source: http://blog.2partsmagic.com/restful-uri-design/

- Axiom 0: Universality 1 — Any resource anywhere can be given a URI
- Axiom 0a: Universality 2 — Any resource of significance should be given a URI.
- Axiom 1: Global scope — It doesn't matter to whom or where you specify that URI, it will have the same meaning.
- Axiom 2a: sameness — a URI will repeatably refer to "the same" thing
- Axiom 2b: identity — the significance of identity for a given URI is determined by the person who owns the URI, who first determined what it points to.
- Axiom 3: non unique — URI space does not have to be the only universal space
- Axiom — In HTTP, GET must not have side effects.
- Axiom — In HTTP, anything which does not have side-effects should use GET
- Axiom: Opacity of URIs — The only thing you can use an identifier for is to refer to an object. When you are not dereferencing, you should not look at the contents of the URI string to gain other information.

— [Tim Berners-Lee’s Axioms](https://www.w3.org/DesignIssues/Axioms.html)


- a domain name that is easy to remember and easy to spell
- short URLs
- easy-to-type URLs
- URLs that visualize the site structure
- URLs that are " hackable " to allow users to move to higher
- levels of the information architecture by hacking off the end of the URL
- persistent URLs that don't change

— [Jakob Nielsen](https://www.nngroup.com/articles/url-as-ui/)


## API URL Design


