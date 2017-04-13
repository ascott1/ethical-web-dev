# Open Source

> A knotty puzzle may hold a scientist up for a century, when it may be that a colleague has the solution already and is not even aware of the puzzle that it might solve.”

― Isaac Asimov

<INSERT INTRODUCTION>

A little bit about the history of OSS

Why is OSS an important part of technology culture?

## Being an Open Source Maintainer

Being an open source maintainer often starts out simply: a developer has an idea for a project or abstracts a piece of a larger project and releases the source code. More often than not, this may be the end of the work. The code is out in the wild for anyone to use, but sometimes that code may be something that other developers find useful. When we release open source code, we are now open source maintainers.

As a project grows in popularity an open source maintainer also becomes a shepherd of the culture that surrounds the project. Sometimes that culture only consists of a handful of users with infrequent interactions and other times it could become something that feels like it needs near constant care and attention.

If an open source maintainer is a cultural shepherd, what are the ethical responsibilities of that role? Open source maintainers have four primary concerns:

- Be kind, welcoming, and friendly
- Include and enforce a code of conduct
- Include a License
- Avoid burnout

### Be Welcoming and Friendly

Perhaps the most important thing we can do as open source maintainers is to be welcoming and friendly to those using our project. The primary ways that we  interact with users are through documentation and our responses to issues. These are both text-based mediums, which means that the reader does not have any of the physical cues of conversation that aid in understanding our tone.

We'll be covering documentation in the next chapter, but in brief when writing documentation for our project we should aim to be as inviting as possible. Users  of our project may come from a range of experience, skill-levels, and cultural/language backgrounds. Great documentation doesn't make assumptions about what the reader may already know or understand. It's ok to provide quick instructions for experienced users who just want to dive in, but also take care in providing explicit instructions or linking to useful resources to help less those with less experience understand the codebase as well as the problem the code is attempting to solve. Doing so will both set the tone for the project itself and aid in minimizing needless issues being created.

Issues and bug fix requests are perhaps the most challenging part of being an open source maintainer, particularly as a project grows in popularity. Issue responses are where we interact with the community most directly. Consider these two common types of issue interactions:

#### Interaction #1: The Frustrated User

_**User**: This software is totally broken since the last update. This needs to be fixed asap._

set a positive example

issue templates

Sometimes it's ok to ignore

#### Interaction #2: The Curt Maintainer

_**User**: I'm having trouble with X in Y environment. I've tried reinstalling with the latest patch but haven't had any luck. Any ideas?

**Maintainer**: This is a known issue. Update the dependencies._

The above may not look too bad. Likely, as a maintainer we're doing this in our spare time and trying to do our best to respond to as many issues as possible. However, to a user a response such as the above may come across as dismissive or even hostile. If they are filing an issue, it is likely that they are either trying to help or have come across a bug that impacts what they are working on. A short response from us can make them less likely to help in the future or serve to compound their frustration. Let's look at how else we could respond, but first let's take a quick detour into communication theory. In his book [Nonviolent Communication: A Language of Life](http://www.nonviolentcommunication.com/) Dr. Marshall B. Rosenberg lays out a process for positive communication. The four key steps to this process are:

1. Observations - Objectively describing the situation.
2. Feelings - Saying how you feel about what you've observed.
3. Needs - The needs that are not being met due to these feelings.
4. Requests - Making clear request for action.

All of the above are done without assigning and form of blame. Using this model we can improve our issue response:

_**Maintainer**: Hi @user, I'm sorry that you are having trouble with X in the Y environment. I've come across this issue before and it can usually be resolved by updating the dependencies. The best way to do that is to remove the dependency directory and reinstall. Here are the commands for doing that:_

```
rm -rf node_modules
npm install
```

_Please let me know if this has resolved your issue._

In this response we acknowledged the user's problem by restating it, addressed the user needs with a concrete recommendation fix and a simple description if they are unfamiliar, and made a clear request for them to verify the fix. Though this response is longer, it would have only taken an extra minute to type out and goes a long way towards building a more welcoming community.


**Note:**
_Sometimes as an open source maintainer we just don't have time to respond to issues in a timely manner. We're busy at work, on vacation, or have a lot happening in our personal lives. This is ok (and good!). We shouldn't feel a persistent obligation in these scenarios. Instead, when you get a chance simply respond to issues with an acknowledgement; "I'm sorry for the slow response. I've been traveling. If this is still an issue do you mind responding and I will see what needs to be done to address it. Thank you!"_

#### Using Bots

For very active open source projects, I love the bot recommendation made by Felix Krause in his article [Scaling open source communities](https://krausefx.com/blog/scaling-open-source-communities). In the article he demonstrates how the [fastlane](https://github.com/fastlane) project uses bots to auto check that new issues contain all of the required information and to close stale issues. This both reduces the burden of response on the maintainer and reduces friction with the community by clearly and consitently following the same guidelines for all issues.

### Open Source Codes of Conduct

The importance of a code conduct

### Open Source Licenses

Why use a license? How to choose?

MIT vs The GPL http://producingoss.com/en/license-quickstart.html

Include a LICENSE file and License in README

### Avoiding Maintainer Burnout

Remember: you set the direction for your project

https://www.youtube.com/watch?v=psN1DORYYV0

https://github.com/jonschlinkert/maintainers-guide-to-staying-positive
https://medium.com/@thejameskyle/dear-javascript-7e14ffcae36c
https://nolanlawson.com/2017/03/05/what-it-feels-like-to-be-an-open-source-maintainer/

## Contributing to Someone Else's Project

https://github.com/jonschlinkert/idiomatic-contributing

filing issues

pull requests

support requests

## Further Reading

- [The Cathedral & the Bazaar](http://shop.oreilly.com/product/9780596001087.do) by Eric S. Raymond
- [Open Source Guides](https://opensource.guide/)
- [Producing Open Source Software](http://producingoss.com/) by Karl Fogel
- [Maintainer's Guide to Staying Positive](https://github.com/jonschlinkert/idiomatic-contributing) by Jon Schlinkert
- [Scaling Open Source Communities](https://krausefx.com/blog/scaling-open-source-communities) by Felix Krause
- [A template for creating open source contributor guidelines](https://opensource.com/life/16/3/contributor-guidelines-template-and-tips) by Safia Abdalla
