# Preserving User Data

Now that we've put a lot of effort into securing and ensuring our user's data is private, we will also want to consider our user's ownership and access to their data. As users pour their personal and work lives into the applications we build, the data this creates can become a reflection of their lives. Our applications may store photos, documents, journals, nots, private reflections, user locations, food preferences, family relationships, meeting information, and connections between all of these things. While this information can be incredibly powerful in continuing to build and improve our applications, our users have a personal investment in the data they have created and shared with us.


Geocities, Gowalla, Delicious examples

https://medium.com/@jazzpazz/with-great-data-comes-great-responsibility-72d3e1c94e27#.q3xjqpurc

https://medium.com/@milesgrimshaw/rights-to-our-data-and-your-own-uber-god-view-dc8416a3751#.raj7nigqw


http://mashable.com/2011/01/12/data-ownership/#UjLRKfXHXgq7

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

## Considering Deceased users

https://www.facebook.com/help/408583372511972/
https://www.facebook.com/help/408583372511972/
https://support.google.com/accounts/troubleshooter/6357590?visit_id=1-636103983508542319-3617250029&hl=en&rd=2

## Archiving and Graceful Shutdown

http://archiveteam.org/

https://web.archive.org/web/20160109002117/http://www.rdio.com/farewell/

http://www.theatlantic.com/technology/archive/2016/05/archiving-a-website-for-ten-thousand-years/482385/

https://medium.com/@craigmod/archiving-our-online-communities-e5868eab4d9a#.otfwpegrr

## Conclusion

## Further Reading
