# Documentation

> Writing is hard work. A clear sentence is no accident.

- William Zinsser, author of _On Writing Well_

I'm going to begin this chapter by describing two common scenarios on the life of a developer.

In our first scenario, meet Harlow. Today is Harlow's first day on a new project. The team has a well-established codebase, a great working environment, and a robust test suite. As Harlow sits down at her desk, she's excited to get up to speed with the team. After the morning stand-up meeting she's pointed to the project's documentation for installation with a slight grimace from her colleague Riley. He mentions that the docs "might be a little out of date, but should hopefully be enough to get you going." Harlow then spends the rest of the day following the documentation until she gets stuck at which point she is forced to dig through code or ask colleagues for guidance. What might have taken a few minutes becomes a day-long exercise in frustration, tampering Harlow's initial excitement.

In our second scenario, meet Harrison. He's working on a web app and finds a library that, at first glance, seems incredibly useful for his project. As he attempts to integrate it with his codebase he discovers that parts of the API seem to be glossed over in the documentation or even undocumented. In the end, he walks away from the project in favor of another solution.

Those these scenarios may be slightly exaggerated, but I'm reasonably certain that many of us can relate. These problems were not primarily caused by low quality code, but rather by poor documentation.

If useful documentation is so important to the success of projects and developer well-being, why don't all projects have it? The answer, I believe, is that like good code, good documentation is difficult and time consuming to write. The goal of this chapter is to convince you that writing good documentation is deserving of your valuable attention as well as provide you with concrete guidelines for doing so.

## The Eight Rules of Good Documentation

In my eyes there are eight rules that we can follow to produce good documentation:

1. Write documentation that is inviting and clear
2. Write documentation that is comprehensive, detailing all aspects of the project
3. Write documentation that is skimmable
4. Write documentation that offers examples of how to use the software
5. Write documentation that has repetition, when useful
6. Write documentation that is up-to-date
7. Write documentation that is easy to contribute to
8. Write documentation that is easy to find

The most important rule of good documentation is for it to **be as inviting as possible**. This means that we should aim to write it in the clearest terms possible without skipping over any steps. We should avoid making assumptions about what our users may know. Sometimes this can seem to be overkill and we may be tempted to say something like "every X developer knows about Y," but we each bring our own background and set of experiences to a project. Though this may result in more verbose documentation, it is ultimately simpler as there is less guesswork involved for developers with all levels of experience.

Our documentation should aim to **be comprehensive**. This means that all aspects of the project are documented. Undocumented features or exceptions can lead to frustration and become a time-suck as users and other developers are forced to read through code to find the answers they need. Fully documenting all features takes away this kind of ambiguity.

When we write documentation that is **skimmable** we help users find the content they need quickly. Making documentation skimmable can be accomplished by using clear headings, bulleted lists, and links. For large project documentation a table of contents or clear navigation will help users to skip straight to what they need, rather than scrolling through a single long document.

Documentation that features **examples** allows users to see how they might use the code themselves. Aim to provide examples of the most common use-cases for the project, while letting the comprehensive documentation detail every possibility.

It is perfectly acceptable to **include some repetition** in our documentation, which the [Write the Docs project](http://www.writethedocs.org/guide/writing/docs-principles/#arid) terms ARID (accepts (some) repetition in documentation). Doing so acknowledges that users may not read the full docs or that some information is relevant in multiple places in the documentation. While good code may be DRY, good writing aims to be clear and sometimes this means repeating ourselves. The Write the Docs project calls out the the difference between writing that is ARID, DRY, and WET in this way:

> The pursuit of minimizing repetition remains valiant! ARID does not mean [WET](https://en.wikipedia.org/wiki/Don't_repeat_yourself#DRY_vs_WET_solutions), hence the word choice. It means: try to keep things as DRY as possible but also recognize that you’ll inevitably need some amount of “moisture” to produce documentation.

Effective documentation is **kept up-to-date**. This is surprisingly challenging. We may begin our project with the best of intentions and great documentation, but as our software evolves and we are quickly iterating it can be easy to fall out step. If you are working as part of an agile development team, I recommend adding documentation to your team's "definition of done." For independent projects, try to treat documentation as an important final step.

Documentation that is **easy to contribute to** is also easy to keep up-to-date. The simplest way to make documentation easy to contribute to is to treat it as code, storing it as text in source control. The site and book [Docs Like Code](http://docslikecode.com/about/) advocates for treating our docs like our code by using source control, automating builds, and applying software development tools and techniques to our documentation practices.

Documentation is only as helpful as it is **easy to find.** Keeping an updated README file and linking to more extensive documentation at the top of the README when necessary helps to keep discoverability simple.

I hope that these guidelines are useful as you draft your project's documentation. Sometimes it is helpful to remember that documentation isn't just for other developers, but often for our future selves as well. When we return to a project after a number of months, we will appreciate the work we put into clear and up-to-date documentation.

## The Importance of the README

For many developers, a project's README will be their introduction to a piece of software. For small projects, the README may be its only form of documentation. Successful READMEs are both informative and inviting, giving the reader a solid understanding of the project and providing the confidence needed to use the software.

Successful READMEs contain a combination of several key elements. Most importantly the README should be up to date and provide a useful getting started guide, written in a warm and welcoming tone. Here are the key components of a good README:

- A brief (1 paragraph or less) description of the project
- A list of the key features of the software
- A getting started guide that details the installation steps, guidelines for usage, and instructions for building and deploying the software, if applicable
- Information on where to go if the user needs help, such as the issue tracker, IRC channel, or a core developer's email address
- Guidelines for how to contribute to the project, including how to file a pull request, coding standards, and how to run the test suite
- A code of conduct for the project that demonstrates inclusion and outlines clear enforcement actions
- A License for the project

Most importantly, a project's README needs to be kept up to date. Few things are more frustrating than discovering that a feature documented in the README has changed or been removed. Marc Esher, a software development manager at the Consumer Financial Protection Bureau, wrote about holding a [README Refresh Day](https://cfpb.github.io/articles/readme-refresh-day/) with the development team. If you work on a team, doing events such as these regularly can be a great way to both improve the contents of your READMEs and to explore software built by other teams.

### README Template

Here's a README template that can be used for your own projects. Feel free to adapt it to your project's needs.

```
# Project Title

Provide a brief (1 paragraph or less), meaningful description of the project
and what it does. If the project has a UI, include a screenshot as well.

If more comprehensive documentation exists, link to it here.

## Features

Describe the core features of the project (what does it do?) in the form of a
bulleted list:

- Feature #1
- Feature #2
- Feature #3

## Getting Started

Provide installation instructions, general usage guidance, API examples, and
build and deployment information. Assume as little prior knowledge as possible,
describing everything in clear and coherent steps. Avoid words such as "just"
and "simple," which can be off putting to users who do not understand the
instructions.

### Installation/Dependencies

How does a user get up and running with your project? What dependencies does
the project have? Aim to describe these in clear and simple steps. Provide
external links.

### Usage

Provide clear examples of how the project may be used. For large projects with
external documentation, provide a few examples and link to the full docs here.

### Build/Deployment

If the user will be building or deploying the project, add any useful guidance.

## Getting Help

What should users do and expect when they encounter bugs or get stuck using
your project? Set expectations for support, link to the issue tracker and
roadmap, if applicable.

Where should users go if they have a question? (Stack Overflow, Gitter, IRC,
mailing list, etc.)

If desired, you may also provide links to core contributor email addresses.

## Contributing Guidelines

Include instructions for setting up the development environment, code
standards, running tests, and submitting pull requests. Aim to be inclusive and
welcoming. It may be useful to link to a seperate CONTRIBUTING.md file. See
this example from the Hoodie project as an exemplar:
https://github.com/hoodiehq/hoodie/blob/master/CONTRIBUTING.md

## Code of Conduct

Open Source projects should follow a code of conduct. Provide a link to the
Code of Conduct for your project. I recommend using the Contributor Covenant:
http://contributor-covenant.org/

## License

Include a license for your project. If you need help choosing a license, use
this guide: https://choosealicense.com/
```

I've open sourced this template and provided guidelines for use at https://github.com/ascott1/readme-template.

## Project Documentation

Larger codebases will require documentation that extends beyond a README. In these instances a good README (or READMEs if the project is split into several smaller codebases) is still an incredibly valuable starting point. It is also  helpful to keep the documentation as near to the code as possible. This may mean generating a static website from plain text or markdown files and storing it in the same code repository or using the repository wiki provided by a source control hosting provider.

One other important aspect of large project documentation is to use it as a means for capturing decision making whenever possible. As developers we are constantly making tradeoffs and decisions that may have impacts on the functionality or use of the codebase. When we capture these ideas, future developers are able to understand the thinking behind this decision. All too often, when decision making is not captured, developers will attempt to re-architect something until they hit the same wall. This "oh, I see why they did it that way" epiphany and wasted energy can be avoided when we accurately capture the thinking behind our decisions.

## When Developers Are Your Customers

For some organizations, developers are our customers. We may build products that handle authentication, messaging, deployment jobs, site availability monitoring, etc. For these types of products, documentation needs to always be treated as a first class citizen, as it is the way our customers learn about our product.

The messaging service Twilio is a great example of this. The [Twilio docs](https://www.twilio.com/docs/) are exemplary, covering a wide range of languages, providing quick start guides, offering interactive tutorials, and a full API reference. The Twilio organization recognizes the value of these docs, employing a team of developers to work on their documentation and the associated tooling full-time.

## Wrapping Up

By focusing on writing good documentation, we are showing empathy for the developers who use our project. Doing so helps to create a project environment that is inclusive, welcoming, and collaborative.

## Further Reading

- [Write the Docs' Documentation Guide](http://www.writethedocs.org/guide/)
- [Docs Like Code](http://docslikecode.com/) by Anne Gentle
- [Writing great documentation](https://byrslf.co/writing-great-documentation-44d90367115a) by Taylor Singletary
- [Beautiful Docs](https://github.com/PharkMillups/beautiful-docs)
