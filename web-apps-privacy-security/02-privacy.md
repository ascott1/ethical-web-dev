Introduction

This has happened to all of us... shopping for sheets and the next time we open one of our favorite websites there's an add for bed linens.

http://www.pewresearch.org/topics/privacy-and-safety/
http://www.pewinternet.org/2014/11/12/public-privacy-perceptions/

## How Users are Tracked

As users browse the web, they are being watched and, as web developers we are often enabling and supporting the surveillance. This isn't a case of tin-foil hat paranoia. As developers we often introduce the code of ad networks to support our work, add social media share buttons that allow users to easily share our site's content, or use analytics software to help us better understand user experience. These sites track user behavior with the intention of providing them with more targeted experience. While this may seem harmless or well intended, this is typically done without the understanding of the end user.

The simplest way that web tracking works is that a user visits a site and that site installs a cookie from a third-party. When we visit another site with the same third-party tracker, the tracker is notified. This allows the third-party to build a unique user profile.

[bubble IMG of tracker shared across sites]

The intention of this tracking is typically to provide more targeted services, advertising, or products. The things we buy, the news we read, the politics we support, our religious beliefs, are often embedded into our browsing history. Without explicit permission, to many, this knowledge feels intrusive.


## What does your browser know about you?

Those aware of user use tracking may take a few steps to attempt to beet the trackers at their own game. Ad blockers such as [uBlock Origin](https://github.com/gorhill/uBlock/) block advertisements as well as third-party advertising trackers. Other browser extensions such as [Privacy Badger](https://www.eff.org/privacybadger) and [Ghostery](https://www.ghostery.com/) attempt to block all third-party beacons from any source. However, even with tools like these, sites may be able to track users based on the unique footprint their browser leaves behind. In fact, the irony of using these tools according to the W3C slide deck [Is preventing browser fingerprinting a lost cause?](https://www.w3.org/wiki/images/7/7d/Is_preventing_browser_fingerprinting_a_lost_cause.pdf), is that "fine grained settings or incomplete tools used by a limited population can make users of these settings and tools easier to track."

Browser's can easily detect the user's IP address, user agent, location, browser plugins, hardware, and even battery level. Web developer Robin Linus developed the site [What every browser knows about you](http://webkay.robinlinus.com/) to show off the level of detail available to developers and site owners. Additionally, the tools [Am I Unique?](https://amiunique.org/) and [Panopticlick](https://panopticlick.eff.org) offer quick overviews of how unique your browser fingerprint is.

<aside>

If you're interested in learning more about privacy and user tracking, I highly recommend the online documentary, [Do Not Track](https://episode1.donottrack-doc.com/).

</aside>


## Do Not Track

With this information about the ways in which users can be tracked, how can we, as web developers, advocate for our user's privacy? My belief is that the first step is to advocate for the respect of the [Do Not Track](https://www.w3.org/TR/tracking-compliance/)(DNT) browser setting. Do Not Track is a browser setting that allows users to specify a preference to not be tracked by the sites they visit. When a user has enabled the Do Not Track setting in their browser, that responds with the HTTP header field `DNT`.

With Do Not Track enabled, browsers send an HTTP header response with a `DNT` value of `1`:

```
Host: "www.example.com"
Accept: "text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8"
Accept-Language: "en-US,en;q=0.5"
Accept-Encoding: "gzip, deflate, br"
DNT: "1"
```

Do Not Track does not automatically disable tracking in a user's browser. Instead, as developers, in our applications, we are then responsible for appropriately handling this user request.


<aside>
**Enabling Do Not Track**

If you are interested in enabling Do Not Track in your browser, or would like to direct others to do so. The site [All About Do Not Track](https://allaboutdnt.com/) has helpful guides for enabling the setting for a range of desktop and mobile browsers.

</aside>

### Detecting Do Not Track

We can easily detect and respond to Do Not Track on the client side of our applications using JavaScript using `navigator.doNotTrack`. This will return a value of `1` for any user who has enabled Do Not Track while returning `0` for a user who has opted in to tracking and `unspecified` for users who have not enabled the setting.

For example we could detect for the Do Not Track setting and avoid setting a cookie in a user's browser:

```
// store user do not track setting s a variables
var dnt = navigator.doNotTrack;

if (dnt !==1) {
  // set cookie only if DNT not enabled
  document.cookie = "example";
}
```

### Respecting Do Not Track

The Mozilla Developer Network helpfully offers [Do Not Track case studies](https://developer.mozilla.org/en-US/docs/Web/Security/Do_not_track_field_guide/Case_studies) and the site DoNotTrack.us provides a [Do Not Track Cookbook](http://donottrack.us/cookbook/), offering a number of company Do Not Track usage scenarios. The examples include practical applications of Do Not Track for advertising companies, technology providers, media companies, and software companies.

http://donottrack.us/cookbook/

### Sites that Respect Do Not Track

- [Twitter](https://support.twitter.com/articles/20169453?lang=en)
- [Medium](https://medium.com/policy/how-we-handle-do-not-track-requests-on-medium-f2b4b4fb7c5e)
- [Pinterest](https://help.pinterest.com/en/articles/we-support-do-not-track)

## Web Analytics

http://piwik.org/blog/2014/01/data-privacy-day-january-28th/

## De-identification

Though avoiding the tracking of users completely is preferred, there may be instances where this choice is outside of our control as web developers. In these cases, we should ensure that any collected user data is de-identified, ensuring that the privacy of our users remains intact. The goal of any de-identification is to ensure that any collected data cannot be used to identify the person who created the data in any way.

However, de-identification is not without its limitations, as de-identified data sets can be paired with other data sets to identify an individual. In the paper [No silver bullet: De-identification still doesn't work](http://randomwalker.info/publications/no-silver-bullet-de-identification.pdf) Arvind Narayanan and Edward W. Felten explore the limits of de-identification. Cryptographic techniques such as [differential privacy](https://en.wikipedia.org/wiki/Differential_privacy) can be used as another layer to help to ensure that individual users cannot be identified within collected datasets.

## User Consent

## Creating a Privacy Policy

Though often left to lawyers...

https://www.eff.org/dnt-policy
https://disconnect.me/icons

## Further Reading

- [DoNotTrack.us](http://donottrack.us/)
- [The emerging ethical standards for studying corporate data](http://www.recode.net/2016/6/14/11923286/facebook-emotional-contagion-controversy-data-research-review-policy-ethics)
- https://www.eff.org/issues/do-not-track
- https://www.w3.org/TR/2015/WD-tracking-compliance-20150714/
