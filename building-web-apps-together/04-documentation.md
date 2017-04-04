# Documentation

Know your audience - write documentation in the simplest terms possible. Don't make assumptions about what users know.

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

Provide a brief (1 paragraph or less), meaningful description of the project and what it does. If the project has a UI, include a screenshot as well.

## Features

Describe the core features of the project (what does it do?) in the form of a bulleted list:

- Feature #1
- Feature #2
- Feature #3

## Getting Started

Provide installation instructions, general usage guidance, API examples, and build and deployment information. Assume as little prior knowledge as possible, describing everything in clear and coherent steps. Avoid words such as "just" and "simple," which can be off putting to users who do not understand the instructions.

### Installation/Dependencies

How does a user get up and running with your project? What dependencies does the project have? Aim to describe these in clear and simple steps. Provide external links

### Usage

Provide clear examples of how the project may be used. For large projects with external documentation, provide a few examples and link to the full docs here.

### Build/Deployment

If the user will be building or deploying the project, add any useful guidance.

## Getting Help

What should users do and expect when they encounter bugs or get stuck using your project? Set expectations for support, link to the issue tracker and roadmap, if applicable.

Where should users go if they have a question? (Stack Overflow, Gitter, IRC, mailing list, etc.)

If desired, you may also provide links to core contributor email addresses.

## Contributing Guidelines

Include instructions for setting up the development environment, code standards, running tests, and submitting pull requests. Aim to be inclusive and welcoming. It may be useful to link to a seperate CONTRIBUTING.md file. See this example from the Hoodie project as an exemplar: https://github.com/hoodiehq/hoodie/blob/master/CONTRIBUTING.md

## Code of Conduct

Open Source projects should follow a code of conduct. Provide a link to the Code of Conduct for your project. I recommend using the Contributor Covenant: http://contributor-covenant.org/

## License

Include a license for your project. If you need help choosing a license, use this guide: https://choosealicense.com/
```

I've open sourced this template and provided guidelines for use at https://github.com/ascott1/readme-template.

## Further Reading

- [A beginner’s guide to writing documentation](http://www.writethedocs.org/guide/writing/beginners-guide-to-docs/)
