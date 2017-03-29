# Code Quality

<INSERT INTRO>

## Code Standards

> Part of being a good steward to a successful project is realizing that writing code for yourself is a Bad Idea™. If thousands of people are using your code, then write your code for maximum clarity, not your personal preference of how to get clever within the spec.

- [Idan Gazit](http://gazit.me/), designer and developer


### Automate Your Standards

Linting!

## Testing

http://docs.python-guide.org/en/latest/writing/tests/

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

### Further Testing reading

- [The Hitchhiker's Guide to Python: Testing Your Code](http://docs.python-guide.org/en/latest/writing/tests/)

## Automation

Continuous integration, etc.

## Pair Programming

## Code Reviews
