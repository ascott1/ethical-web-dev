# Accessibility

> The power of the Web is in its universality. Access by everyone regardless of disability is an essential aspect.

— Tim Berners-Lee, Inventor of the World Wide Web

Building accessible web sites and applications means making those sites available to users regardless of physical ability. This covers a broad range of disabilities, such as visual, physical, auditory, cognitive, and age related disabilities. When we build with accessibility in mind, we make an ethical decision of inclusion. Alternatively, when we choose to ignore accessibility, it excludes people with disabilities from participating in the web.

Today, as web users we access government services, educational resources, bank transactions, social interactions, work tasks, health care, entertainment, and more through our web browsers. As the web continues to play an increasingly large role in our daily lives, this causes inaccessible websites to be a hurdle to fully participating in society. With the importance the web plays in our society, it has become our responsibility as developers to ensure its equal access to all.

The W3C has summarizes the social issues around web accessibility in [three principles](https://www.w3.org/WAI/bcase/soc#social):

-  It is essential that the Web is accessible in order to provide equal access and equal opportunity to people with disabilities.
- The Web is an opportunity for unprecedented access to information for people with disabilities.
- The Web is an opportunity for unprecedented interaction for people with disabilities.

The W3C has also called out that the United Nations [Convention on the Rights of Persons with Disabilities](https://www.un.org/disabilities/convention/conventionfull.shtml) expresses that accessibility across the web has become a human right. Specifically it states:

> To enable persons with disabilities to live independently and participate fully in all aspects of life, States Parties shall take appropriate measures to ensure to persons with disabilities access, on an equal basis with others […] to information and communications, including information and communications technologies and systems[…].

> States Parties shall take all appropriate measures to ensure that persons with disabilities can exercise the right to freedom of expression and opinion, including the freedom to seek, receive and impart information and ideas on an equal basis with others and through all forms of communication of their choice[…].

When done correctly, an accessible web not only provides equal access to services and information, but also empowers those with disabilities.


### Further reading:

- [Social Factors in Developing a Web Accessibility Business Case for Your Organization](https://www.w3.org/WAI/bcase/soc)
- [Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html)


## Broadening the scope of accessibility

The need for accessibility is not limited to those with permanent disabilities. Accessible web interfaces may benefit a range of users.

As of the [2010 census](http://www.census.gov/prod/cen2010/briefs/c2010br-09.pdf), there are 17 million people 75 years of age and older living in the United States. World wide, over [8% of the earth’s total population](http://www.indexmundi.com/world/demographics_profile.html) falls into the 65 and above category. This age group has consistently grown as a percentage of the total population, creating an increasing market segment. With an aging population, there are several factors that can impact the use of the web, most notable motor and vision impairments. By building with accessibility in mind, we are able to accommodate users of all ages.

In addition to those with permanent or age related disabilities, many users may have temporary disabilities. Often these may be related to an injury where vision or motor abilities are impaired. 

### Further reading

- [News for Betty](https://melodykramer.github.io/how-betty-who-is-89-gets-her-news/)
- [Meeting the Needs of Aging Web Users](https://www.w3.org/WAI/older-users/Overview.php)


## POUR

The guiding principle of building accessible web applications is referred to as the [POUR principle](https://www.w3.org/TR/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head), stating for Perceivable, Operable, Understandable, and Robust. Following these guidelines allow us to build web sites and applications that are usable by all.

> Perceivable - Information and user interface components must be presentable to users in ways they can perceive.
This means that users must be able to perceive the information being presented (it can't be invisible to all of their senses)

Links: two perceptions

> Operable - User interface components and navigation must be operable. This means that users must be able to operate the interface (the interface cannot require interaction that a user cannot perform)

Tab-able interface

> Understandable - Information and the operation of user interface must be understandable. This means that users must be able to understand the information as well as the operation of the user interface (the content or operation cannot be beyond their understanding)

Simplicity? Reading level?

> Robust - Content must be robust enough that it can be interpreted reliably by a wide variety of user agents, including assistive technologies.This means that users must be able to access the content as technologies advance (as technologies and user agents evolve, the content should remain accessible)

range of browsers, devices, screen readers, etc


## Understanding WCAG 2.0

> Rather than issuing a simple checklist of "do’s and don'ts," WCAG 2 instead establishes a series of Success Criteria to address various online content barriers. The Success Criteria are written as testable statements that are not technology-specific. This approach ensures that content authors are not told that they cannot do a particular thing, but instead offers means and suggestions for ensuring that whatever is created can be made accessible.

— https://soap.stanford.edu/guidelines-standards/understanding-wcag-20

- [WCAG 2.0](https://www.w3.org/TR/WCAG20/)
- [Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/)

Overview of WCAG requirements. Make this non-intimidating.

Explain conformance levels.



## ARIA

https://www.w3.org/TR/WCAG20-TECHS/aria

## Using a screen reader to navigate the web

- [ChromeVox](http://www.chromevox.com/) & [ChromeVox tutorial](http://www.chromevox.com/tutorial/index.html)

(NOTE: Be sure to include instructions for testing a screen reader *visually* so as not to exclude anyone with auditory disabilities)

### OS screen readers

- [VoiceOver for Mac](https://www.apple.com/accessibility/osx/voiceover/): CMD + F5 to enable
- [Narrator for Windows](http://windows.microsoft.com/en-us/windows/hear-text-read-aloud-narrator#1TC=windows-8)

### Other popular screen readers

GitHub as an example of an accessible web application

Medium.com article page - just adding a "Skip to article" link would be a *huge* improvement!

### Using a screen reader to apply for social assistance programs

[Applying for Social Security Benefits](https://secure.ssa.gov/iClaim/dib) &  seems to be a good example of accessible content!

At the time of writing [NY.gov's site](http://www.ny.gov/) as well as the NY State's [Office of Temporary and Disability Assistance site](http://otda.ny.gov/accessibility.asp) are beautiful, full of accessible information, and touts an [accessibility policy](http://www.ny.gov/accessibility). Unfortunately, the site that handles the applications for core services such as school meals and nutrition assistance is [anything but accessible](https://mybenefits.ny.gov/mybenefits/NewAccountCreation!input.nysmybw).


## Writing accessible markup



## Accessibility checklist

http://webaim.org/standards/wcag/checklist
http://a11yproject.com/checklist.html

## Accessibility tools

- tota11y
- pa11y
- aXe
- WAVE
- a11y
- [Chrome Accessibility Developer Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en)

## Automating accessibility tests

As an npm script in package.json:

```javascript
"scripts": {
    "accessibility": "a11y localhost:3000",
  }
```

As a Gulp task:

```javascript
var exec = require('child_process').exec;

gulp.task('accessibility', function (){
  exec('a11y localhost:3000', function(err, stdout, stderr) {
    console.log(stdout);
    console.log(stderr);
  });
});
```

Paired with a continuous integration system, such as [Travis CI](https://travis-ci.com/), we could run these accessibility checks against every build, failing if there are accessibility errors.


## Convincing your organization

From <https://www.w3.org/WAI/bcase/soc#social>

> Web accessibility provides improved access, interaction, and social inclusion for the people described above, which is a primary aspect of corporate social responsibility (CSR).

> Corporate social responsibility, also called corporate citizenship, corporate responsibility, or responsible business, generally means conducting business ethically and operating an organization in such a way that treats internal and external stakeholders ethically, increases human development, and is good for society and the environment. Web accessibility can impact an organization's employees, stockholders and board members, suppliers and vendors, partners and collaborators, customers, and others. Thus Web accessibility is an integral part of CSR in demonstrating an organization's commitment to providing equal opportunities.

> Just as an accessible website can demonstrate CSR, an inaccessible website can undermine an organization's other CSR efforts.

> When an organization's website is not accessible, it further excludes people with disabilities from society. When an organization's website is accessible, it empowers people with disabilities to participate in society. Providing an accessible website is one way an organization can demonstrate that it strives to meet the access needs of a diverse society.

> An organization's efforts in Web accessibility are a public relations opportunity to increase its positive image, which can increase website use. The Social Factors page discusses Web accessibility as a social issue and an aspect of corporate social responsibility (CSR). CSR has been shown to improve financial performance, enhance brand image and reputation, increase sales and customer loyalty, increase ability to attract and retain employees, and provide access to capital and funding. Additional perspectives on CSR, such as statistics that show how CSR impacts customers, are available on the Web.

## In Summary

## Videos of users

- http://www.dingoaccess.com/accessibility/refreshable-braille-and-the-web/
- https://dotsub.com/view/9787ebec-941f-4e04-a5dc-f6ed7fde7247

### Additional resources

- [W3C Web Accessibility Initiative](https://www.w3.org/WAI/)
- [W3C Web Accessibility Guidelines](https://www.w3.org/standards/webdesign/accessibility)
- [W3C Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/)
- [The Accessibility Project](http://a11yproject.com/)
- [HIKE](http://accessibility.parseapp.com/)
- [WebAIM](http://webaim.org/)
- [MDN ARIA Resources](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)
