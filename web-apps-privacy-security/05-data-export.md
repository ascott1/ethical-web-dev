# Preserving User Data

Now that we've put a lot of effort into securing and ensuring our user's data is private, we will also want to consider our user's ownership and access to their data. As users pour their personal and work lives into the applications we build, the data this creates can become a reflection of their lives. Our applications may store photos, documents, journals, nots, private reflections, user locations, food preferences, family relationships, meeting information, and connections between all of these things. While this information can be incredibly powerful in continuing to build and improve our applications, our users have a personal investment in the data they have created and shared with us.

In 2009 the site GeoCities was shuttered. GeoCities was as an early free web hosting platform and was considered an important piece of early web history. Though Yahoo, who had acquired GeoCities in 1999, provided guidance for how to preserver their sites elsewhere, many of the sites were no longer actively maintained, ensuring that they would be lost forever. In light of this, several projects such as the [Internet Archive](https://archive.org/web/geocities.php), [Archive Team](http://www.archiveteam.org/index.php?title=GeoCities_Project), [ReoCities](http://reocities.com/), and [OoCities](http://www.oocities.org/) undertook Herculean efforts to archive or mirror the original GeoCities content.

In 2011 the social check-in service Gowalla [announced](http://blog.gowalla.com/post/13782997303/gowalla-going-to-facebook) that the service would be shutting down. Gowalla was an early competitor with Facebook and had a passionate and enthusiastic user base. In a blog post, Gowalla founder, Josh Williams stated that "[w]e plan to provide an easy way to export your Passport data, your Stamp and Pin data (along with your legacy Item data), and your photos as well." Unfortunately, despite the best of intentions of the Gowalla team, the ability to export data was not added before the service was fully shut down, causing all Gowalla user data to be lost.

These are just two of many interesting examples of site closures or significant feature changes that can cause user data to be lost. As developers, we are entrusted with user data. By providing users a means to export their data, we are able to give them more control over how and where it is used.


## Data Ownership

Why owns the data generated within our application? Though it may be easiest to say "the user," this can become an increasingly complicated question when we consider things such as collaborative documents, online discussions, and shared calendars, who have may have an initial creator but ultimately have multiple maintainers. What about the sites themselves? Sometimes a Terms of Service may insist on ownership or exclusive rights to a user's created content. As part of Facebook's Terms of Service, the company enforces exclusive rights to any content created within or posted to the site:

> For content that is covered by intellectual property rights, like photos and videos (IP content), you specifically give us the following permission, subject to your privacy and application settings: you grant us a non-exclusive, transferable, sub-licensable, royalty-free, worldwide license to use any IP content that you post on or in connection with Facebook (IP License).

In doing this, we take the power away from the user and assert ownership over the content they have created. Though there is a business case for this, it comes at a potential cost to our users. The creator of the Web, Tim Berners-Lee, has spoken out in favor of user-owned data, stating that “the data that [firms] have about you isn’t valuable to them as it is to you.”

If we take this perspective, we should aim to open user data to our users and provide a means to export it from our site in an open format.

In his article, [Rights to Your Data and Your Own Uber ‘God’ View](Rights to Your Data and Your Own Uber ‘God’ View), Miles Grimshaw suggests adapting a Creative Commons style license for personal data, which would be adopted by services collecting this data.

You are free to:

**Download**  —  free access to your raw data in standard file formats

**Share**  —  copy and redistribute the data in any medium or format

**Adapt ** —  remix, transform, and build upon the data

Under the following terms:

**Attribution** —  You must provide a sign-up link to the application

The, since acquired, start-up Kifi had a forward thinking approach to user data, stating in a [blog post](https://medium.com/kifi-engineering/exporting-user-data-71a060bdb774#.1w2hbekka) that:

> Any service that manages your data has an implicit contract with users: you give us your data and we’ll organize it, but it’s still your data; we are just stewards for it. At Kifi, one way we try to fulfill our end of this contract is by making sure users can export their data for offline use (or so they can import it into another service).

These ideas are not limited to start-ups or small services. In 2012 Twitter introduced the ability to [download an archive of your Tweets](https://blog.twitter.com/2012/your-twitter-archive), giving users both permenant access to their Twitter content as well as the potential ability to import it into another service. Google also provides the ability to [download an archive](https://support.google.com/accounts/answer/3024190?hl=en) of the data created with any of its services including the ability to easily store the archive in common file sharing applications such as DropBox, Google Drive, and Microsoft OneDrive.

By giving our users ownership and access to their data, we can be better stewards of that information. This aids us in creating long-lasting user content and opens up the potential for users to adapt and use their data in novel and interesting ways. Most importantly, by providing access to user data we are able to give ownership of the data our users create directly to the user.

## Deleting User Data

An inevitable reality is that some users will want to stop using the services we build. In many cases, these users may simply allow their accounts to decay, but other users will explicitly seek to delete their accounts and associated information. When a user does delete their account, we should also delete it from our databases, rather than simply hide the user's content within our site or application. Doing so will be more in line with user expectations and ensures that user data is removed in the case of a data breach.

## Archiving and Graceful Shutdown

At the beginning of the chapter, we looked at a few web application shut downs and how the loss of their data impacted users. According to the United States Small Business Administration, [40% of small business fail after three years](http://www.bls.gov/bdm/us_age_naics_00_table7.txt). In the world of tech start-ups, that number is significantly higher, as reportedly [9 out of 10 start-ups fail](http://www.forbes.com/sites/neilpatel/2015/01/16/90-of-startups-will-fail-heres-what-you-need-to-know-about-the-10/#7751c49955e1). This also fails to take into account, web applications that are acquired or owned and closed by large companies.

The group Archive Team works to catalog and preserve digital history, but also keeps a [Deathwatch](http://archiveteam.org/index.php?title=Deathwatch) of sites risking shutdown and advice for individuals on [backing up our data](http://archiveteam.org/index.php?title=Introduction). Though this is a wonderful project, we cannot assume that users will back-up their data. When our services are closing down we can do so gracefully. The music streaming service Rdio closed its doors in 2015, but in doing so offered a [farewell](https://web.archive.org/web/20160109002117/http://www.rdio.com/farewell/), which included the ability for users to download CSV files of things such as their playlists and saved music to be imported into another service. As the site [Hi.co](http://hi.co/) shuttered, it's founder Craig Mod committed to keeping the archive on the web for the next ten years, making individual contributions exportable, and producing five nick-plated books of the site to be preserved. In [an article about the shutdown](https://medium.com/@craigmod/archiving-our-online-communities-e5868eab4d9a#.c2tg22g46), Mod wrote:

> At the same time we understand the moral duty we took on in creating Hi.co — in opening it up to submissions and user generated content. There was an implicit pact: You give us your stories about place, and we’ll give you a place to put your stories. This was not an ephemeral pact.

Though we may not choose to nickel-plate our own service's contents, providing exports will ensure that users are able to preserve their data if they choose to do so.

## Further Reading

- [With Great Data Comes Great Responsibility](https://medium.com/@jazzpazz/with-great-data-comes-great-responsibility-72d3e1c94e27#.ls4gmwey7) by Pascal Raabe
- [Archiving a Website for Ten Thousand Years](http://www.theatlantic.com/technology/archive/2016/05/archiving-a-website-for-ten-thousand-years/482385/) by Glenn Fleishman
- [Preserving Digital History](http://chnm.gmu.edu/digitalhistory/preserving/index.php) by Daniel J. Cohen and Roy Rosenzweig
