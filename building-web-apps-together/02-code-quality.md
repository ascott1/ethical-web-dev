# Code Quality

In the book _Let's Talk About Love: A Journey to the End of Taste_, music journalist Carl Wilson mulls over what it means for something to be good. The book focuses on the Celine Dion album that it is named after, which has sold 31 million copies and is one of the top-selling albums of all time. Despite this immense success, music critics such as Wilson (and likely many of us reading this), are quick to dismiss Celine Dion's music for a number of reasons. The reason for this disparity is that taste in entertainment and art is subjective. Each of us brings our own unique cultural experiences along with us when we enjoy (or don't) these things.

https://plato.stanford.edu/entries/hume-aesthetics/

If things such the worthiness of art and entertainment are subjective, what about the quality of code? Is good code subjective or objective? This can be a challenging topic, as much like music we all bring our own experience and assumptions to the discussion of what constitutes "beautiful" code. With that in mind, I've sought to identify a few object measures of code quality. Doing so allows us to remove the risk of needless or even unhealthy debate that subjective taste introduces to the development process. Instead, when following these guidelines, discussions can focus on outcomes and a shared set of principles.

Good code does the following:

- Follows a set of standards
- Uses version control
- Is well tested
- Utilizes automated checks

Additionally, since code is often written in a collaborative or team environment, we can leverage the processes of code reviews and pair programming. Ultimately, code is intended to be executed by machines, but read by humans. When we write code that follows these guidelines, we create a codebase that is collaborative, understandable, and can safely be changed without unintended consequences

## Code Standards

> All code in any code-base should look like a single person typed it, no matter how many people contributed.

- Rick Waldron, author of [idiomatic.js](https://github.com/rwaldron/idiomatic.js)

Perhaps one of the most straightforward things we can do to improve our code quality is to follow a set of standards. Standards are useful when working with a team, as they set clear expectations for all team members and minimize syntax debates in code reviews. Following standards creates code that is easier to read and understand, as there is not a mis-mash of styles across the codebase. When creating an organization style guide, I recommend treating it as code and storing the guides in version control. This enables easy contributions, history tracking, the ability to open pull requests, and issue tracking for proposed changes. For individual projects following a code standard is useful too as it can help us catch syntax errors and to avoid the types of sloppy mistakes that can result when working alone.

Following a standard does not mean creating a document from scratch. Nearly every language has a number of style guides available that range from small open source projects to official documents created by large organizations. Some languages, such as Python, have predominantly settled on a single standard (PEP 8). Below is a list of style guides in various popular languages. This is far from complete, but I hope that it gives you a jumping off point. I've tried to provide a mix of community and corporate guidelines whenever possible.

In short, successful standards follow these guidelines:

- Automate checks
- Are stored in version control
- Are easy to read and follow
- Leverage community guidelines

### Multiple Languages

- [Google's Style Guides](https://github.com/google/styleguide)
- [Khan Academy's Style Guides](https://github.com/Khan/style-guides/blob/master/style/javascript.md)
- [Thoughtbot's Style Guides](https://github.com/thoughtbot/guides)

### JavaScript

- [JavaScript Standard Style](https://standardjs.com/)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- [JavaScript Quality Guide](https://github.com/bevacqua/js)
- [Idiomatic.js](https://github.com/rwaldron/idiomatic.js)
- [Node Style Guide](https://github.com/felixge/node-style-guide)
- [Douglas Crockford's Code Conventions](http://javascript.crockford.com/code.html)

### Python

- [PEP 8](https://www.python.org/dev/peps/pep-0008/)
  - [The Elements of Python Style](https://github.com/amontalenti/elements-of-python-style)
- [The Hitchhiker's Guide to Python: Code Style](https://python-guide.readthedocs.io/en/latest/writing/style/)

### Ruby

- [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide)
- [GitHub's Ruby Style Guide](https://github.com/github/rubocop-github/blob/master/STYLEGUIDE.md)
- [Shopify's Ruby Style Guide](https://shopify.github.io/ruby-style-guide/)

### PHP

- [WordPress PHP Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/)
- [FIG Standards](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md)
- [PHP the Right Way](http://www.phptherightway.com/)
- [CodeIgniter Style Guide](https://www.codeigniter.com/user_guide/general/styleguide.html?highlight=style%20guide)

### Go

- [Effective Go](https://golang.org/doc/effective_go.html)
- [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)

### Java

- [Java Programming Style Guidelines](http://geosoft.no/development/javastyle.html)
- [Twitter's Java Style Guide](https://github.com/twitter/commons/blob/master/src/java/com/twitter/common/styleguide.md)
- [Android's Code Style for Contributors](https://source.android.com/source/code-style.html)

### HTML & CSS Standards

- [Code Guide by @mdo](http://codeguide.co/)
- [Khan Academy's CSS Style Guide](https://github.com/Khan/style-guides/blob/master/style/css.md)
- [Primer](http://primercss.io/guidelines/)
- [Idiomatic CSS](https://github.com/necolas/idiomatic-css)
- [Airbnb's CSS + SASS Style Guide](https://github.com/airbnb/css)
- [CSS: The Good Parts](https://github.com/bevacqua/css)

If you work for an organization that does not follow a set of standards, I recommend researching various standards in the language of your choice and introducing them to your colleagues. As a team you may choose to follow a single standard or may prefer to adapt bits and pieces from several standards into your organization's own standard. Though this may seem tedious and introduce debate, when done correctly it can be an excellent team building exercise and a way of creating common expectations.

### Automate Your Standards

Standards are only as useful if they are put into practice. Introducing a set of standards is a great first step, but next we must ensure that they are followed. Manually reviewing code for standards acceptance is a tedious process that code linting can help us to avoid. There are two places in which linting should take place: our text editors and anywhere our application's test suite is run.

Text editors can be configured to run linting inline against our standards. Most text editors have packages available for linting that can be configured to a set of standars (or are automatically configured to a specific standard). Doing so allows us to see errors inline and correct them quickly.

Even if we aim to lint our standards in real-time with our text editor, it is possible to miss something. With this in mind, we should also run our linting anywhere that our test suite is run. This is particularly useful in build pipelines (which are discussed later in the chapter). Doing so will cause our tests to fail when standards are not followed. If this is new to you, it may feel extreme, but as mentioned in the beginning of the chapter this has the advantage of removing the need for human interaction or discussion from something that can be subjectively measured.

## Version Control

## Testing

**NOTE**:
_For the purpose of this book we'll be focusing on unit testing and functional testing. In addition to these there are other forms of software testing that are worth exploring for your application, such as performance testing (encompassing things such as stress testing, scalability testing, load testing) security testing, and regression testing._

### Unit Testing

### Browser and Functional Testing

As web developers, our applications are executed in a web browser. This is unique as it creates a wide range of variable environments, screen resolutions, and browser types in which our application could be run. Our site may be accessed by a brand new laptop, viewed through a 4k resolution monitor, over a fiber internet connection. Alternately, it could be viewed on an outdated smartphone, using a modified stock browser, on a 3G connection.

The challenge of creating resilient applications that work in a variety of environments is what makes web development challenging and rewarding. If we seek to create inclusive applications, those accessing our sites through outdated browsers and devices may be the people who need the greatest access to our services.

To ensure the level of access that we expect, we will want to run functional tests of our applications in a variety of operating systems and browsers. Let's look at two approaches for doing this, using browser testing services and visiting a device labs.

**NOTE:**
_Emphasizing the need for browser testing does not equate to our sites or applications working the same in every browser. If you are interested in taking a tiered approach to browser support, I highly recommend reading about BBC News' approach in their article [Cutting the Mustard](http://responsivenews.co.uk/post/18948466399/cutting-the-mustard)._

#### Browser Testing Services

There are a number of services that allow you to test a range of browsers on a number of operating systems without installing each of them or running virtual machines. These services allow you to load a URL and click through them in many combinations of mobile and desktop browsers.

- [Browser Stack](https://www.browserstack.com/)
- [Sauce Labs](https://saucelabs.com/)
- [Browserling](https://www.browserling.com/)

Clicking through a site can be effective for small sites, but as your project grows you may want to automate these types of tests. [Selenium](http://docs.seleniumhq.org/) is a popular tool for automating browser actions. My preferred setup is to use [WebDriver.io's](http://webdriver.io/) Node/JavaScript Selenium bindings to drive functional tests in combination with one of the above services. Sauce Labs offers a [helpful guide](https://saucelabs.com/blog/accelerate-multi-browser-testing-using-sauce-labs-and-webdriverio) to using WebDriver.io as does [Browser Stack](https://www.browserstack.com/automate/webdriverio).

Regardless of method, integrating a browser testing service into our workflow allows us to test our sites and applications on a range of browsers that we may not otherwise have access to.

#### Device Labs

![img/device-lab.png](img/device-lab.png)
> The Device Lab at Clearleft. Photo by Jeremy Keith

Though browser testing services are incredibly useful, it can be a rewarding (or frustrating!) experience to test our applications on a range of physical devices. It's particularly helpful to test on some of the low-powered, budget-priced tablets and phones that are popular with real users. Since few of us have a shelf full of devices, many device labs have popped up at co-working centers, makerspaces, and local businesses. The site [Open Device Lab](https://opendevicelab.com/) seeks to compile these labs that are publicly accessible. If there isn't one in your area and you work for a co-located company with a number of employees, you may also consider building your own lab. Start with a few donated devices that you and co-workers may have collecting dust on the shelf

### Test-Driven Development (TDD)

Test-driven development (TDD) is a development methodology that emphasizes writing the test for a feature prior to implementing it. This ensures high-levels of code coverage, allows a developer to make changes in confidence, and ensure feature completion. The TDD process works as follows:

1. Add a test
2. Run all tests and see if the new test fails
3. Write the code
4. Run tests
5. Refactor code
6. Repeat

There are many great books and resources on TDD, so I won't retread that content here. If you are new to the TDD concept, I recommended exploring resources and materials for TDD in your chose language or framework. Though it can be a paradigm shift, TDD can add a newfound level of robustness and confidence to our development process.

## Automation

Continuous integration, etc.

## Pair Programming

## Code Reviews

## Further Reading

- Working Effectively with Legacy Code by Michael Feathers
- [The Hitchhiker's Guide to Python: Testing Your Code](http://docs.python-guide.org/en/latest/writing/tests/)
