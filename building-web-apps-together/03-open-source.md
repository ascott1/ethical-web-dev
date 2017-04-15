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

When we come across these types of issues and requests it can be very frustrating. This is our work and is something that we likely take pride in. Not only that, but we've shared it publicly and freely, while working on it in our precious spare time.  That spare time is time away from family, friends, and other things that we love outside of programming. As such, it can feel upsetting or even infuriating when someone is overly critical or makes demands of our projects. The most important thing we can do when we come across these types of issues is to react calmly. On the Internet this is often referred to as "don't feed the trolls." There is nothing wrong with closing an issue with a simple "I'm sorry this does not meet your needs."

We can also take a proactive approach towards mitigating these types of issue creators by including templates for issues and pull requests in our projects. [GitHub](https://github.com/blog/2111-issue-and-pull-request-templates) offers the ability to include templates in your project that will create an outline for every new issue and pull request that is created. Good templates will provide a framework for contributors to create issues and contribute to the project, potentially alleviating the lack of context that these often contain. The developer Steve Mao has created a helpful set of [example templates](https://github.com/stevemao/github-issue-templates) and a collection of example issue and pull request templates has been collected by the project [Awesome GitHub Templates](https://github.com/devspace/awesome-github-templates).

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

For very active open source projects, I love the bot recommendation made by Felix Krause in his article [Scaling open source communities](https://krausefx.com/blog/scaling-open-source-communities). In the article he demonstrates how the [fastlane](https://github.com/fastlane) project uses bots to auto check that new issues contain all of the required information and to close stale issues. This both reduces the burden of response on the maintainer and reduces friction with the community by clearly and consistently following the same guidelines for all issues.

### Open Source Codes of Conduct

Perhaps one of the most important documents that can be included in a project is a code of conduct. A good code of conduct will establish clear expectations for positive interaction among the community as well as outcomes for those who fail to meet those expectations. The goal of the code of conduct is to provide guidelines for an open and inclusive community around our projects.

Programmer, advocate, and consultant Ashe Dryden describes the four key components of a successful Code of Conduct in her article [Codes Of Conduct 101 + FAQ](https://www.ashedryden.com/blog/codes-of-conduct-101-faq) as needing these four parts:

- A statement of unacceptable behavior
- Information on how the policy will be enforced
- Information on how and whom to make an incident report to
- Training and reference materials for organizers, staff, and volunteers on how to respond to incident reports

Let's look at how we can apply each of these to our open source projects. For establishing a statement of unacceptable behavior and including information on how the policy will be enforced, I recommend using or basing your policy upon the [Contributor Covenant](http://contributor-covenant.org/). The Contributor Covenant is a Creative Commons licensed resource that includes a pledge of inclusion, standards of behavior, examples of both model and unacceptable behavior, responsibilities of the maintainers, information on how to report incidents, and enforcement information. To include the Contributors Covenant in your project, I recommend adding a `code_of_conduct.md` file the to the project files along with a link in the project README that states:

```
## Code of Conduct

This project adheres to the [Contributor Covenant 1.4][code-of-conduct.md]. By participating, you are expected to honor this code. Please report unacceptable behavior to user@example.com.
```

Including the code of conduct is only the first step. We must also be prepared and informed to take action should an incident occur. For these incidents, the Django Project has a very useful [enforcement manual](https://www.djangoproject.com/conduct/enforcement-manual/). For large or active projects, I recommend adapting this manual to meet the needs of your project and publicly sharing the commitment to enforcement. For a project with multiple maintainers, it is critical that the entire team is well-versed in both the code of conduct as well as the enforcement actions that may be taken.

### Open Source Licenses

Some people in the open source community feel _very_ strongly about a particular license. I am not here to indoctrinate you into using a particular license, but simply to encourage you to use _a_ license. The Open Source Initiative maintains a [canonical list](https://opensource.org/licenses/alphabetical) of licenses approved by the organization, the most popular of which are:

- Apache License 2.0
- BSD 3-Clause "New" or "Revised" license
- BSD 2-Clause "Simplified" or "FreeBSD" license
- GNU General Public License (GPL)
- GNU Library or "Lesser" General Public License (LGPL)
- MIT license
- Mozilla Public License 2.0
- Common Development and Distribution License
- Eclipse Public License

The benefit of applying a license is that it allows you to create the terms by which your project can be used. The MIT license, for example, allows users to use your code in any way they choose as long as they provide some form of attribution. By contrast, the GPL requires that any derivative work license itself under the same terms, which effectively prohibits closed-source projects form using code licensed under the GPL. By choosing a license for your code, you are indicating how it may be used and credited. Doing so also allows opens our projects up to being used (or not) by organizations who may be unable to do so with unlicensed code.

If you are unsure of which license to apply to your projects, I recommend the guide at [choosealicense.com](https://choosealicense.com). The site, created by GitHub, guides users to popular licenses based on specific needs and concerns.

The simplest way to include a license in your project is to include the license text or a declaration of which license is being used at the bottom of the project's README. You may also include the full text of the license in a `LICENSE` at the top-level of the project.

### Avoiding Maintainer Burnout

If all of the above sounds exhausting, that's because it often is. Being an open source maintainer is a lot of work and is often done as an extra-curricular hobby outside of typical working hours. This means that open source development is often relegated to those who are privileged with free-time, which may not be an ongoing possibility as a developer's life changes. Due to the demands, time commitments, and, at times, guilt that comes along with being an open source maintainer, many eventually experience burnout.

If this all feels familiar, I'd encourage you to read the perspective of developers who have battled with open source burnout:


- [Maintainer's Guide to Staying Positive](https://github.com/jonschlinkert/maintainers-guide-to-staying-positive) by Jon Schlinkert
- [What it feels like to be an open-source maintainer](https://nolanlawson.com/2017/03/05/what-it-feels-like-to-be-an-open-source-maintainer/) by Nolan Lawson
- [How to Avoid Burnout Managing an Open Source Project](https://thenewstack.io/darker-side-open-source/) by Dawn Foster
- [Dear JavaScript](https://medium.com/@thejameskyle/dear-javascript-7e14ffcae36c) by James Kyle

If you have been contributing to open source and feel burnt out, I'd offer these three pieces of advice:

1. **Take care of your health and well-being.** Things like sleep, nourishment, and time with friends and family are important. Though the speed of change in web development can cause us to feel like we must be constantly involved, being a well-rounded and healthy human will help us to also be better developers.
2. **It's OK to ignore things.** As issues and pull requests pile up, we may become overwhelmed or even guilty by a lack of action. Nearly every time I've spoken to the author of a popular open source project, they mention a feeling of guilt for not addressing a bug or responding to outstanding issues. Though it may be difficult to do, it's important to let go of the nagging feeling that these create and accept that it's impossible for one person to respond to every need of a project.
3. **Don't be afraid to deprecate a project.** When a project has completely lost your interest or attention, it may be better to deprecate the project or hand it over to other maintainers. The easiest way to do this is to place a large **DEPRECATED** notice in the project description and README. You can also offer to transfer ownership of the project if someone else is interested in taking it over. This signifies to users that you will no longer be responding to issues or contributing new features and bug-fixes. Doing so is not admitting defeat, but rather allowing ourselves to move on to different things.

## Contributing to Someone Else's Project

https://github.com/jonschlinkert/idiomatic-contributing

filing issues

pull requests

support requests

## Further Reading

- [The Cathedral & the Bazaar](http://shop.oreilly.com/product/9780596001087.do) by Eric S. Raymond
- [Open Source Guides](https://opensource.guide/)
- [Producing Open Source Software](http://producingoss.com/) by Karl Fogel
- [Maintainer's Guide to Staying Positive](https://github.com/jonschlinkert/maintainers-guide-to-staying-positive) by Jon Schlinkert
- [Scaling Open Source Communities](https://krausefx.com/blog/scaling-open-source-communities) by Felix Krause
- [A template for creating open source contributor guidelines](https://opensource.com/life/16/3/contributor-guidelines-template-and-tips) by Safia Abdalla
