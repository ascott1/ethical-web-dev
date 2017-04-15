# Code Quality

In the book _Let's Talk About Love: A Journey to the End of Taste_, music journalist Carl Wilson mulls over what it means for something to be good. The book focuses on the Celine Dion album that it is named after, which has sold 31 million copies and is one of the top-selling albums of all time. Despite this immense success, music critics such as Wilson (and likely many of us reading this), are quick to dismiss Celine Dion's music for a number of reasons. The reason for this disparity is that taste in entertainment and art is subjective. Each of us brings our own unique cultural experiences along with us when we enjoy (or don't) these things. The 18th Century philosopher David Hume wrote about subjectiveness in his essay _Of the Standard of Taste_, stating that "Beauty is no quality in things themselves: It exists merely in the mind which contemplates them."

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

Early in my web development career, I would be developing a project in a folder on my machine and want to test out some major changes. To do so, I would make a copy of the folder, named something like "Project-EXPERIMENT." By the end of a project I often ended up with a dozen such folders, each with slightly different versions of my code. It worked OK when I was working alone, but as soon as another developer was involved, we would wind up emailing files to each other or FTPing them to a server, hoping that our changes didn't accidentally negate the changes made by one another. As you can imagine, this was a less than ideal way to work and collaborate.

Using version control irons out the wrinkles in the above process. Notably version control brings:

- Increased and straightforward collaboration
- Ability to reverse changes
- Ability to "branch" versions of the project
- Code conflict resolution

If you are new to version control, I recommend using Git, which can be combined with open source code hosting tools such as [GitHub](https://github.com/) or [GitLab](https://about.gitlab.com/). There are many great resources for learning Git, among them:

- [Try Git](https://try.github.io/)
- [Git-It](https://github.com/jlord/git-it-electron)
- [Codeacademy's Learn Git](https://www.codecademy.com/learn/learn-git)

## Testing

Writing about testing is like writing about flossing. We all know that we _should_ do it, but, for many of us, at the end of a busy day sometimes it's easier to skip over it. "I'll write those tests tomorrow," we say to ourselves, only to tackle the next important feature the next morning. Or perhaps, you don't yet see the value in testing, instead thinking "I can see that it works - why do I need to run tests?" If either of these descriptions sound familiar, that's ok. They certainly describe outlooks I've taken at different points of my professional career. My hope is that in this section to demonstrate the value of testing and look at two useful types of tests: unit tests and functional/browser tests.

**NOTE**:
_For the purpose of this book we'll be focusing on unit testing and functional testing. In addition to these there are other forms of software testing that are worth exploring for your application, such as performance testing (encompassing things such as stress testing, scalability testing, load testing) security testing, and regression testing._

### Why Test At All?

This is the big question: why test at all? When we develop web sites and applications, we are running the site locally on our machine and are able to see it working. This _is_ a form of testing, but as you may have encountered, it is incomplete, particularly as we build sites that have interactive features and user input. When we write tests we can safely ensure that our code works as intended and doesn't break pre-existing features.

### Unit Testing

The most straightforward way to think of a unit test is as a way to test a very small aspect of our code. Typically this would be testing that an individual function or method returns the expected value. Consider the following example, written in JavaScript (roughly based on the [Mocha](https://mochajs.org/) testing framework with the [Chai](http://chaijs.com/) assertion library).

We'd like to write a function (called `stayPositive`) that always returns a positive number when passed a value. Let's first write our test, which expects that a positive number (2) is equal to calling our function and passing it the value 2.

```
it('should return a positive number when passed a positive', function() {
  expect(stayPositive(2)).to.equal(2);
});
```

Currently this test would fail, so let's write the function:

```
var stayPositive = function(num) {
  return num;
}
```

If we ran our test again it would pass, but what if we write a test with a negative number?

```
it('should return a positive number when passed a negative', function() {
  expect(stayPositive(-2)).to.equal(2);
});
```

In the above example we are passing a value of -2 and expecting our function to return a positive value of 2. Based on our code, this would fail, so we can re-write our function to account of negative numbers:

```
var stayPositive = function(num) {
  if(num > 0) {
    return num;
  } else {
    return -num;
  }
}
```

Now, if we were to run our unit tests they would pass! Hooray! But what if the user passed a 0 or a string? How would our program handle those?

```
it('should return 0 when passed 0', function() {
  expect(stayPositive(0)).to.equal(0);
});

it('should return an error when passed a string', function() {
  expect(stayPositive('Hello')).to.be.an('error');
});
```

We can then modify our code to handle these types of errors. Writing unit tests such as these allows us to ensure our applications are robust and are able to handle a variety of potential outcomes.

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

**NOTE:**
_TDD or BDD? You may also come across the term Behavior Driven Development (BDD). There are many debates on what exactly the difference is between these two approaches. I prefer the one described by developer Josh Davis in his post [The Difference Between TDD and BDD](http://joshldavis.com/2013/05/27/difference-between-tdd-and-bdd/). Essentially TDD is the process and BDD is a more verbose approach where the tests describe the expected behavior. These tend to read like a sentence. Astute readers may notice that in the unit testing example above we followed a TDD process with a BDD syntax. I encourage you to explore both and find the approach the works best for you._

## Automation

Linting against your standards and writing tests are only useful when they are run. When actively developing it's easy to forget to run a test suite against our changes before pushing or making a codebase. Thankfully, automation is something that computers excel at, so we can remove this responsibility from ourselves. For open or closed source projects using a pull request model, we can use automated tooling that will alert us when a pull request contains failing tests or linting errors. This will ensure that this code does not enter the codebase before these errors are corrected. When used as part of a continuous integration pipeline, we can run our tests and cause a build to fail when our tests fail, ensuring that we don't ship broken code.

For projects using GitHub and the pull request model, I recommend [TravisCI](https://travis-ci.org/). Travis supports many languages and is free for open source projects. It can also be configured to deploy to S3 and Heroku environments. For internal environments, I recommend [Jenkins](https://jenkins.io/). Jenkins is a highly extensible, self-hosted, continuous integration pipeline tool.

There are a number of alternatives available in a range of languages. As always, do due diligence and find the tool that works best for you and your collaborators. The important aspect is automating our tests and ensuring they are passing before integration and release.

## Pair Programming

Pair programming can be an extremely beneficial process, which results in improved code and increased team collaboration. Pair programming is the act of two developers programming together. In this process, one person _drives_ by physically typing code into the computer. While the second person _navigates_ by talking through the code that is being written with the driver. When done well, pair programming is extremely effective.

There are a few requirements for pair programming to be effective.

First, both developers must treat each other with respect and as equals. Perhaps the biggest and most failure in pair programming that I have seen is when experienced developers are dismissive of ideas made by junior developers. Successful pair programming happens when both parties enter it as an opportunity to learn and grow.

Second, the pairing must be done in a welcoming environment. Do you use Vim but your partner uses an IDE? Each person needs to work in an environment in which they feel comfortable and able to fully contribute. Just as arrogance can cause pair programming to be ineffective, so can feelings of inadequacy.

Lastly, both developers must be fully engaged in the programming activity. If the navigator finds themselves not paying attention, checking their phone, or doing something counter-productive the activity is detrimental. Successful pair programming requires the attention of both developer's full attention.

**NOTE:**
_Some organizations practice full-time pair programming (sometimes part of the "Extreme Programming" methodology). As a natural introvert, I've never been a big fan of this, preferring instead shorter bursts of pair programming on a semi-regular or as-needed basis. If you are interested in implementing pair programming at your work place, start small. Regularly ask colleagues to pair with you and offer to drive. This takes the stress off of the colleague. Once the benefits are clear, your colleagues are more likely to do the same._

### Remote Pair Programming

Pair programming isn't just for those who are co-located. In fact, as a remote developer for the past 4 years I've found pairing to be one of the best ways to connect with my remote colleagues. There are a number of tools that enable remote pair programming. I've listed a few below, but you may find that you need to experiment to find a tool that works well for you and your colleagues.

Remote pair programming tools:

- [Screenhero](https://screenhero.com/)
- [Floobits](https://floobits.com/)
- [Motepair](https://atom.io/packages/motepair)
- [TeamViewer](https://www.teamviewer.com/en/)

## Code Reviews

Often before code is merged into a codebase it is reviewed by other developers. In a Git workflow this typically comes as part of the pull request process. This type of critique process can be challenging. Writing code is both a mental and creative process over which we feel a sense of pride. When someone is critical of something we have written it can be frustrating or even upsetting. As a person reviewing code, we are challenged to conduct a thorough review to ensure that the code meets standards, expectations, and fulfills requirements while not being overly harsh. How then do we participate in successful code reviews both as a reviewer and reviewee?

The design and development firm Thoughtbot has a thorough [code review guide](https://github.com/thoughtbot/guides/blob/master/code-review/README.md) that breaks down recommendations into three categories: everyone, having your code reviewed, and reviewing code. I've re-printed the Thoughtbot guide, with permission and some modification, as they perfectly summarize the approach that I would recommend.

### Guidelines for Everyone Involved in a Code Review

Both the code author and the reviewer play an equally important role in the code review process. To keep the process positive and effective, all participants should aim to do the following:

- Accept that many programming decisions are opinions. Discuss tradeoffs, which
  you prefer, and reach a resolution quickly.
- Ask good questions; don't make demands. ("What do you think about naming this
  `:user_id`?")
- Good questions avoid judgment and avoid assumptions about the author's
  perspective.
- Ask for clarification. ("I didn't understand. Can you clarify?")
- Avoid selective ownership of code. ("mine", "not mine", "yours")
- Avoid using terms that could be seen as referring to personal traits. ("dumb",
  "stupid"). Assume everyone is intelligent and well-meaning.
- Be explicit. Remember people don't always understand your intentions online.
- Be humble. ("I'm not sure - let's look it up.")
- Don't use hyperbole. ("always", "never", "endlessly", "nothing")
- Don't use sarcasm.
- Keep it real. If emoji, animated gifs, or humor aren't you, don't force them.
  If they are, use them with aplomb.
- Talk synchronously (e.g. chat, screensharing, in person) if there are too many
  "I didn't understand" or "Alternative solution:" comments. Post a follow-up
  comment summarizing the discussion.

### Guidelines for Having Your Code Reviewed

Having our code reviewed can be a stressful process. Remember that the review is of the code, not you personally. With that in mind aim to follow these guidelines:

- Be grateful for the reviewer's suggestions. ("Good call. I'll make that
  change.")
- Seek to understand the reviewer's perspective.
- Explain why the code exists. ("It's like that because of these reasons. Would
  it be more clear if I rename this class/file/method/variable?")
- Try to respond to every comment.
- Extract some changes and refactorings into future tickets/stories.
- Link to the code review from the ticket/story. ("Ready for review:
  https://github.com/organization/project/pull/1")
- Push commits based on earlier rounds of feedback as isolated commits to the
  branch.
- Wait to merge the branch until Continuous Integration tells you the test suite has passed.
- Merge once you feel confident in the code and its impact on the project.

### Guidelines for Reviewing Code

Reviewing someone else's code is a responsibility. Do be an effective code reviewer it is critical to first understand the author's perspective. Put yourself in their shoes and aim to communicate in a clear, non-judgmental fashion. Beginning with this empathetic perspective, also aim to do the following in your review:

- Understand why the change is necessary (bug, user
experience, refactor).
- Communicate which ideas you feel strongly about and those you don't.
- Identify ways to simplify the code while still solving the problem.
- Avoid focusing on trivial issues or things outside of the purview of the changes being reviewed.
- If discussions turn too philosophical or academic, move the discussion offline. In the meantime, let the author make the final decision on alternative implementations.
- Offer alternative implementations, but assume the author already considered
  them. ("What do you think about using a custom validator here?")
- Sign off on the pull request with a `:thumbsup:` emoji or "Ready to merge" comment.


## Further Reading

- Working Effectively with Legacy Code by Michael Feathers
- [The Hitchhiker's Guide to Python: Testing Your Code](http://docs.python-guide.org/en/latest/writing/tests/)
- [Code Review in the Lab](https://mozillascience.github.io/codeReview/intro.html) by Mozilla Science
- [Effective Code Reviews without the Pain](http://www.developer.com/tech/article.php/3579756/Effective-Code-Reviews-Without-the-Pain.htm) by Robert Bogue
