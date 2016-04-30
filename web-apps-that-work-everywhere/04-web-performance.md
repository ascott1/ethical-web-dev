# Web performance

introduction

Mobile bandwidth

https://paul.kinlan.me/the-web-in-india-anecdote-1/


Facebook’s empathy lab: 

- https://www.washingtonpost.com/news/the-switch/wp/2015/03/31/facebooks-empathy-lab-how-facebook-designs-for-disabled-users/
- http://www.businessinsider.com/facebook-2g-tuesdays-to-slow-employee-internet-speeds-down-2015-10?r=UK&IR=T

- avoid render blocking
- file size
- number of resources
- server response time
- perceived performance

## File size

As of writing, the average web page requires a user to download roughly 2.3MB worth of data[^1]. Using this metric, the first 5.25 inch hard drive, the 1980 Seagate ST-506, would be able to hold just two modern web pages. 

![Seagate ST-506 Hard Drive](img/st-506.jpg)

With varying connection speeds around the world, the cost of accessing our site’s can differ. The tool [What does my site cost?](https://whatdoesmysitecost.com) seeks to provide insight into the real-world data costs of sites accessed over a mobile connection.

Here is the cost of a few different sites when accessed in various parts of the world:

[TODO: FORMAT AS TABLE]

[Wikipedia Article](https://whatdoesmysitecost.com/test/160430_G5_b0f0622361ae1d0fffe2eeaf5d43fbbb)
Size: 0.23MB
Canada: $0.03
Botswana: $0.02
USA: $0.01
France: $0.00

[Verge Apple Watch Review](https://whatdoesmysitecost.com/test/160430_95_260026b8ebd320ee3087393fdea12525)
Size: 8.02MB
Canada: $0.98
Botswana: $0.60
USA: $0.51
France: $0.16

[Google+](https://whatdoesmysitecost.com/test/160430_VQ_5597117e2bdb01ddfe4b3400826d84e3)
Size: 2.05MB
Canada: $0.25
Botswana: $0.15
USA: $0.13
France: $0.04

To decrease the footprint of our websites, we can aim to:

1. Minimize the number of resources
2. Optimize images and fonts
3. Serve responsive images
4. Leverage gzip and caching

By putting these four best practices in action, we ensure that our site’s users are transferring the lowest amount of data from our servers to their devices.

### Number of Resources

- HTTP requests and DNS lookups
- the pre’s
    - prefetch 
    - preconnect
    - prerender
    - preload

[^1]: http://www.httparchive.org/trends.php

### http2

### Optimizing Images and Fonts

### Responsive Images

### Gzip and Caching

## Page rendering

- CSS in the `<head>`
- JS at the bottom of the page

## Perceived Performance

Critical rendering path

## Testing Performance

### Initial test

- Open the site in Chrome. Open DevTools, and do a hard refresh while the Network tab is open.
- Run a test on webpagetest.org.

### WebPagetest

http://www.webpagetest.org/


### Other Tools

## Performance Budgets

https://timkadlec.com/2013/01/setting-a-performance-budget/

> people perceive tasks as faster or slower when there’s a least a 20% time difference. So, let’s take our fastest times and try to beat them by 20%.

http://danielmall.com/articles/how-to-make-a-performance-budget/
https://timkadlec.com/2014/11/performance-budget-metrics/

## Further Reading

- [The Web Site Obesity Crisis](http://idlewords.com/talks/website_obesity.htm)
- [Smaller, Faster Websites](https://bocoup.com/weblog/smaller-faster-websites)
- [Designing for Performance: The Basics of Page Speed](http://designingforperformance.com/basics-of-page-speed/)
- [Google Web Fundamentals: Performance](https://developers.google.com/web/fundamentals/performance/)
- [W3C Web Performance Working Group](https://www.w3.org/2010/webperf/)