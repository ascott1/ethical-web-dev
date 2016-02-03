# Accessibility

## Introduction

POUR principle: Perceivable, Operable, Understandable, and Robust.

## Accessibility as a social issue

- [W3's take on the social issues surround accessibility](https://www.w3.org/WAI/bcase/soc#social)
- [W3's Designing for Inclusion](https://www.w3.org/WAI/users/Overview.html)

## Understanding WCAG 2.0

[WCAG 2.0](https://www.w3.org/TR/WCAG20/)

## Using a screen reader to navigate the web

- [ChromeVox](http://www.chromevox.com/) & [ChromeVox tutorial](http://www.chromevox.com/tutorial/index.html)

### OS screen readers

- [VoiceOver for Mac](https://www.apple.com/accessibility/osx/voiceover/): CMD + F5 to enable
- [Narrator for Windows](http://windows.microsoft.com/en-us/windows/hear-text-read-aloud-narrator#1TC=windows-8)


GitHub as an example of an accessible web application

Medium.com article page - just adding a "Skip to article" link would be a *huge* improvement!

### Using a screen reader to apply for social assistance programs

[Applying for Social Security Benefits](https://secure.ssa.gov/iClaim/dib) &  seems to be a good example of accessible content!

At the time of writing [NY.gov's site](http://www.ny.gov/) as well as the NY State's [Office of Temporary and Disability Assistance site](http://otda.ny.gov/accessibility.asp) are beautiful, full of accessible information, and touts an [accessibility policy](http://www.ny.gov/accessibility). Unfortunately, the site that handles the applications for core services such as school meals and nutrition assistance is [anying but accessible](https://mybenefits.ny.gov/mybenefits/NewAccountCreation!input.nysmybw).


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

## Reading/Viewing

- [W3C Web Accessibility Guidelines](https://www.w3.org/standards/webdesign/accessibility)
- [The Accessibility Project](http://a11yproject.com/)
- [HIKE](http://accessibility.parseapp.com/)
- [WebAIM](http://webaim.org/)
- [MDN ARIA Resources](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)
- [The WAI Forward](https://www.smashingmagazine.com/2014/07/the-wai-forward/)
- [W3C Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/)
