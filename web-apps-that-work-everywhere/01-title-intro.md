# Introduction

In 2007, at the 3GSM conference in Barcelona, Tim Berners-Lee, the creator of the Web, gave a [keynote address on the mobile web](https://www.w3.org/2007/Talks/0222-3gsm-tbl/text). In this talk, which happened 6 months prior to the release of the original iPhone, Berners-Lee states:

> The Web is designed, in turn, to be **universal**: to include anything and anyone. This universality includes an independence of hardware device and operating system… and clearly this includes the mobile platform. It also has to allow links between data from any form of life, academic, commercial, private or government. It can't censor: it must allow scribbled ideas and learned journals, and leave it to others to distinguish these. It has to be independent of language and of culture. It has to provide as good an access as it can for people with disabilities.

This idea of universality has become even more critical in our increasingly diverse world of web access. By design, the Web works across platforms and devices, easily connecting rich documents with one another and providing access to users around the world. Despite this universal default, as web developers, it is our responsibility to build a web that is accessible to all. But before we look at how of building an everywhere Web, let’s consider why.

In the United States, where I live, nearly 1 in 5 adults own a smartphone, but either do not have access to high-speed internet at home or have limited access other than their cell phone[^1]. Additionally, mobile devices are heavily depended upon for access to a wide range of social and cultural services. According to the [Pew Internet Study](http://www.pewinternet.org/2015/04/01/us-smartphone-use-in-2015/), smartphone users report that in the past year:

- 62% have used their phone to look up information about a health condition.
- 57% have used their phone to do online banking.
- 44% have used their phone to look up real estate listings or other information about a place to live.
- 43% to look up information about a job.
- 40% to look up government services or information.
- 30% to take a class or get educational content.
- 18% to submit a job application.

[^1]: http://www.pewinternet.org/2015/04/01/us-smartphone-use-in-2015/

Meanwhile, smartphone ownership in emerging and developing nations has dramatically increased over recent years, rising to a median of 37% in 2015[^2] with worldwide 3G coverage reaching 69%[^3].This rise in access can come at a cost, as fixed-broadband is 3 times more expensive and mobile data is twice as expensive in developing countries than in developed countries[^3].Worldwide Internet speeds can vary wildly as well ranging from an average of nearly 40 Mbit/s in Korea to 0.09 Mbit/s in Zambia[^3].

**It’s predicted that by 2020 there will be 7.8 billion mobile-connected devices, exceeding the world’s population**[^4].

[^2]: http://www.pewglobal.org/2016/02/22/smartphone-ownership-and-internet-usage-continues-to-climb-in-emerging-economies
[^3]: http://www.itu.int/en/ITU-D/Statistics/Documents/facts/ICTFactsFigures2015.pdf
[^4]:https://www.cisco.com/c/en/us/solutions/collateral/service-provider/visual-networking-index-vni/mobile-white-paper-c11-520862.html

In his talk [Small, Faster Websites](https://bocoup.com/weblog/smaller-faster-websites), Mat "Wilto" Marquis describes the challenge of building for an everywhere web in this way:

> Building massive, resource-heavy sites means excluding millions of users that have only ever known the web by way of feature phones or slightly better—users paying for every kilobyte they consume; users that already have to keep tabs on which sites they need to avoid day-to-day because of the cost of visiting them. I don’t mean some nebulous hand-wavy “bandwidth cost,” either—I mean actual economic cost.

Despite the challenges of building for a diverse, multi-device Web served over a variety of connection speeds, we can make user-centered choices that enable greater access to our sites and data. We can do this through:

- Exposing permanent, human readable, deep links
- Building sites that are responsive to a range of viewport sizes
- Valuing the performance of our site’s and the bandwidth they consume
- Leveraging off-line first capabilities that support varying network conditions

Through this report we’ll explore these topics and take a practical approach to putting them into practice.