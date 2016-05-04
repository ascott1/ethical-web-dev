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

[TheVerge.com Apple Watch Review](https://whatdoesmysitecost.com/test/160430_95_260026b8ebd320ee3087393fdea12525)
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

Perhaps the biggest impact we can have on file size and data transfer is to limit the number of resources sent to the user.

- HTTP requests and DNS lookups
- the pre’s
    - prefetch 
    - preconnect
    - prerender
    - preload

[^1]: http://www.httparchive.org/trends.php

### http2

### Optimizing Files, Images, and Fonts

Once we have reduced the number of http requests being made in our site, the next step is to optimize the files we server. We can do this by minimizing CSS and JS resources, optimizing and and serving proper images, and making good use of web fonts when used.

#### Minimizing Files

Though white space and line breaks make CSS and JavaScript files readable to humans, they are necessary for the browser to properly parse them. To reduce the file size of these resources we should minimize them for our production sites.

There are several desktop and web applications for minimizing CSS and JavaScript.

[LIST SOME DESKTOP APPS]
- [UglifyJS](http://marijnhaverbeke.nl//uglifyjs)

Desktop and web tools may be great for simple sites or those that aren’t updated frequently, but to minimize effort we can integrate minification into a build process for our site. How this is done may depend on your site’s stack, Ruby on Rails, for example, has an [asset pipeline](http://guides.rubyonrails.org/asset_pipeline.html) for the minification of assets. A common cross-framework approach is to use a build tool such as [Gulp](http://gulpjs.com/), [Grunt](http://gruntjs.com/), or [npm scripts](https://docs.npmjs.com/misc/scripts). For these build tools there are a number of minification plugins. Here are a few that I’ve used with success in the past:

- [node-minify](https://www.npmjs.com/package/node-minify) - A Node interface for minifying both CSS and JavaScript, which utilizes a number of popular compression algorithms.
- [uglify-js](https://www.npmjs.com/package/uglify-js) - A command line utility, written in JavaScript, for minifying JavaScrip.
- **Gulp**: [gulp-clean-css](https://www.npmjs.com/package/gulp-clean-css) - A css minification plugin for Gulp.
- **Gulp**: [gulp-uglify](https://www.npmjs.com/package/gulp-uglify) - A JavaScript minification plugin for Gulp.
- **Grunt**: [grunt-contrib-cssmin](https://www.npmjs.com/package/grunt-contrib-cssmin) - A CSS minification plugin for Grunt.
- **Grunt**: [grunt-contrib-uglify](https://www.npmjs.com/package/grunt-contrib-uglify) - A JavaScript minification plugin for Grunt.

#### Images

Images comprise the largest file sizes on a typical web page. [ADD COOL STAT]. By using images well and reducing their file sizes, we can significantly reduce the bandwidth they consume.
To do this we should use the proper image formats, optimize images to reduce file size, and serve the image size needed by the browser.

When creating images, we need to consider their content and choose the most appropriate format. 

- **JPG**: Use for photographs.
- **PNG**: Use as the default for most other static images and images that require transparency.
- **GIF**: Use for simple images. Supports transparency and animation.
- **SVG**: Small file size that scales well and is supported all modern browsers and Internet Explorer 9+.

Once we have chosen the proper file format for an image, we should optimize the image file. Optimizing reduces the file size of an image by applying compression and removing unnecessary information such as metadata, embedded thumbnails, and color profiles. There are a number of desktop and online tools that you may use to manually optimize images:

- [ImageOptim](https://imageoptim.com)
- [imagemin-app](https://github.com/imagemin/imagemin-app)
- [PNG Gauntlet](http://pnggauntlet.com/)
- [Tiny PNG](https://tinypng.com/)
- [ImageAlpha](https://pngmini.com/)
- [JPEG-Optimizer](http://www.jpeg-optimizer.com/)

For sites using a front-end build process, such as Gulp, Grunt, or npm scripts we can bake image optimization into our build process. The node package [imagemin](https://www.npmjs.com/package/imagemin) provides a utility for minimizing images in a number of build environments:

- **Command line interface:** [imagemin-cli](https://github.com/imagemin/imagemin-cli)
- **Gulp**: [gulp-imagemin](https://www.npmjs.com/package/gulp-imagemin)
- **Grunt:** [grunt-contrib-imagemin](https://www.npmjs.com/package/grunt-contrib-imagemin)

#### Responsive Images

Serve different image sizes at different viewport widths (responsive images)


Fonts:

> Some browsers will wait a predetermined amount of time (usually three seconds) for the font to load before they give up and show the text using the fallback font-family. But just like a loyal puppy, WebKit browsers (Safari, default Android Browser, Blackberry) will wait forever (okay, often 30 seconds or more) for the font to return. This means your custom fonts represent a potential single point of failure for a usable site.

https://www.keycdn.com/blog/web-font-performance/

[57% of websites now use custom fonts](http://httparchive.org/trends.php#perFonts)

Read: 

- https://www.zachleat.com/web/
- https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/webfont-optimization
- https://www.filamentgroup.com/lab/font-loading.html
- https://www.bramstein.com/writing/web-font-loading-patterns.html

```
@font-face {
  font-family: 'My Web Font';
  font-style: normal;
  font-weight: 400;
  src: local('My Web Font'),
       url('/fonts/myfont.woff2') format('woff2'), 
       url('/fonts/myfont.woff') format('woff'),
       url('/fonts/myfont.ttf') format('ttf'),
       url('/fonts/myfont.eot') format('eot');
}
```


### Gzip and Caching

https://jakearchibald.com/2016/caching-best-practices/

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