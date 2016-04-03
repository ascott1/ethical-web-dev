
# Accessibility


> The power of the Web is in its universality. Access by everyone regardless of disability is an essential aspect.

— Tim Berners-Lee, Inventor of the World Wide Web


Building accessible web sites and applications means making those sites available to users regardless of physical ability. This covers a broad range of disabilities, such as visual, physical, auditory, cognitive, and age related disabilities. When we build with accessibility in mind, we make an ethical decision of inclusion. Alternatively, when we choose to ignore accessibility, it excludes people with disabilities from participating in the web.

Today, as web users, we access government services, educational resources, bank transactions, social interactions, work tasks, health care, entertainment, and more through our web browsers. As the web continues to play an increasingly large role in our daily lives, this causes inaccessible websites to be a hurdle to fully participating in society. With the importance the web plays in our society, it has become our responsibility as developers to ensure its equal access to all.

The W3C summarizes the social issues around web accessibility in [three principles](https://www.w3.org/WAI/bcase/soc#social):

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
- [MYTH: Accessibility is “blind people”](http://a11yproject.com/posts/myth-accessibility-is-blind-people/)


## Web Content Accessibility Guidelines

In 2008 the W3C released an update to the Web Content Accessibility Guidelines, commonly referred to as (WCAG) 2.0. This document covers a range of success criteria for creating accessible web content. Rather than focusing on specific technologies, the document offers a suggestions for making all web sites and applications more accessible.

### POUR

The guidelines and success criteria of building WCAG 2.0 accessible web applications are organized around the [POUR principle](https://www.w3.org/TR/UNDERSTANDING-WCAG20/intro.html#introduction-fourprincs-head). POUR stands for Perceivable, Operable, Understandable, and Robust. Following these guidelines allow us to build web sites and applications that are usable by all.

> Perceivable - Information and user interface components must be presentable to users in ways they can perceive.

Perceivable means that a user should be provided the opportunity to perceive the content of our web applications. To do this, we must ensure that the information being presented is visible to their senses. When we limit content to a single sense, we run the risk of alienating users.

One common use case of perception is providing written transcripts of audio material or captioning video material. Perhaps a less obvious example is the style of links across the web. A link that is only a different color from the text would be imperceptible to a color blind users[^colorblind]. Instead, we should be sure to alter the color as well as provide an underline to the link. This provides a perceptible option to the color blind user.

![Perceptible link demonstration](img/link-perception.png)
<figcaption>Retaining the default link behavior of including an underline allows them to be perceptible to color blind users.</figcaption>

[^colorblind]: Color blindess affects a significant portion of the population, specifically those born male. Roughly 8% of male born people are said to have some form of color blindness. https://en.wikipedia.org/wiki/Color_blindness#Epidemiology

> Operable - User interface components and navigation must be operable.

By being operable, all users are able to operate and navigate the interface of the web application. Perhaps a simple example of this is providing users the ability to easily “tab through” our sites, by navigating through the page using only the `tab` keyboard key. A user who is unable to operate a mouse or track pad may navigate sites using only the keyboard. Ensuring that our sites are keyboard accessible is one way to ensure that they are  operable by all users.

> Understandable - Information and the operation of user interface must be understandable.

When we build understandable interfaces, we follow common development patterns of hierarchy and user interaction. Though, when working with a team, these may often fall in the domain of a designer, as developers we make choices about how we develop these patterns.

One common anti-pattern is using form label `placeholder` text in the place of a form label.

Here is a form element, properly marked up with a label and placeholder text:

```
<label for="password">Password:</label>
<input type="text" name="password">
```

Here is one that uses the placeholder to replace the label:

```
<input type="text" name="password" placeholder="Password">
```

![Image of placeholder as label](img/placeholder-field.png)

The use of placeholder text in the place of labels raises several potential [usability and accessibility concerns](https://www.nngroup.com/articles/form-design-placeholders/) due to low contrast, extra cognitive burden as users must recall the purpose of the field, and unreliable screen reader support. By making solid development decisions such as proper form markup, we can develop more understandable sites.

> Robust - Content must be robust enough that it can be interpreted reliably by a wide variety of user agents, including assistive technologies.

By building robust web applications, we build [future friendly](http://futurefriendlyweb.com/) sites that are device and browser agnostic. When we develop without a specific platform in mind and do not limit our browser support, we are able to build sites that are accessible to any user. This is a topic that we will cover in depth in a future title, “Building Web Applications that Work Everywhere.”

### WCAG conformance

WCAG 2.0 is separated into three levels of conformance, based on success criteria that is defined in the [WCAG 2.0 specification](https://www.w3.org/TR/WCAG20/):

- Level A – Level A provides basic web accessibility support. This meets all Level A success criteria, or provides an alternate content version that does.
- Level AA – Level AA addresses the most common accessibility issues. This meets all Level A and Level AA success criteria or provides an alternate content version that does.
- Level AAA – Level AAA provides highest level of web accessibility support for users. This meets all Level A, Level AA, and Level AAA success criteria, or provides an alternate version.

It is worth noting that the W3C does not recommended that Level AAA conformance be required for entire sites as it is not possible to satisfy all Level AAA Success Criteria for some content. If you choose to put an accessibility policy in place for your organization, I recommend aiming for Level AA support.

### WCAG 2.0 Guidelines

The WCAG 2.0 guidelines are classified according to the POUR principle. Guideline 1 encompasses areas of perception, Guideline 2 covers areas of operation, Guideline 3 is directed at ensuring understanding, and Guideline 4 is targeted at the robustness of the application. Below are the specific guidelines from WCAG 2.0:

- Guideline 1.1 Text Alternatives: Provide text alternatives for any non-text content
- Guideline 1.2 Time-based Media: Provide alternatives for time-based media
- Guideline 1.3 Adaptable: Create content that can be presented in different ways (for example simpler layout) without losing information or structure
- Guideline 1.4 Distinguishable: Make it easier for users to see and hear content including separating foreground from background.
- Guideline 2.1 Keyboard Accessible: Make all functionality available from a keyboard.
- Guideline 2.2 Enough Time: Provide users enough time to read and use content.
- Guideline 2.3 Seizures: Do not design content in a way that is known to cause seizures.
- Guideline 2.4 Navigable: Provide ways to help users navigate, find content, and determine where they are.
- Guideline 3.1 Readable: Make text content readable and understandable.
- Guideline 3.2 Predictable: Make Web pages appear and operate in predictable ways.
- Guideline 3.3 Input Assistance: Help users avoid and correct mistakes.
- Guideline 4.1 Compatible: Maximize compatibility with current and future user agents, including assistive technologies.

WebAIM.org provides a [helpful checklist](http://webaim.org/standards/wcag/checklist) of recommendations for implementing HTML-related principles and techniques for WCAG 2.0 conformance, along with the associated support level.

### Further WCAG reading

- [Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/)
- [WCAG 2.0](https://www.w3.org/TR/WCAG20/)
- [Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/)

## Building Empathy

### Using just your keyboard to navigate the web

For many desktop users, navigating through web sites with a keyboard is an essential function. These users may have motor disabilities, vision disabilities, limb loss, or injuries that make mouse usage impractical. By ensuring that our sites are keyboard navigable, we are increasing the availability of our applications to these users.

The basics of keyboard navigation are simple:

- Press the Tab key to navigate through the page
- Press Tab + Shift to go backwards in your navigation

Using the tab key, we are able to navigate to links, buttons, and form elements on the page. This allows us to quickly interact with elements on the page.

There are a few ways that as developers we can ensure the best possible keyboard navigation experience for our users. Primarily, we should aim to:

- Keep or apply custom :focus styles
- Be aware of navigation order and length
- Use default navigation elements

#### Keep or Add :focus style

When a user navigates to an element with the Tab key, it is visually indicated using a `:focus` style. By default, in most browsers this either a thin dotted line a blue highlighted border around the focused element. Unfortunately, it has become a fairly common trend to remove this focus style by applying an `outline:0` or `outline:none` in CSS. This can be avoided by either retaining that default behavior or adding a custom focus style through CSS.

```
a:focus {
	background-color: #01FF70;
}
```

##### Further reading:

- [Quick Tip: Never remove CSS outlines](http://a11yproject.com/posts/never-remove-css-outlines/)

#### Navigation Order and Length

When a user navigates through a site using the keyboard, the order and length of keyboard navigable items become critically important. Imagine the frustration of a user pressing tab through every link presented in a sidebar (such as Twitter or Facebooks “trends”) before being able to access the main content of the application. By using a “skip to content link,” in our applications we can provide an extra guidepost that directs our users to the most valuable content.

Skip to navigation links are hidden links that when “tabbed” to or read by a screen reader, allow the user to skip to the main content of the page, rather than needing to navigate through navigation and other content that occurs earlier in the document order. These can be visually hidden, appearing only when a user presses the tab key.

To begin, add a skip to navigation link at the top of the document, linking directly to the main content of the page:

```
<body>
  <a href="#main" class="skip-link">Skip to main content</a>
  …
  <main id="main" role="main>
    <h1>Page Content</h1>
    …
  </main>
</body>
```

For styles, we can first hide the skip link visually while keeping it visible to screen readers:

```
.skip-link {
	position: absolute;
  width: 1px;
  height: 1px;
  margin: 0;
  overflow: hidden;
  clip: rect(1px, 1px, 1px, 1px);
}
```

Then make it appear visually when the link receives focus with the Tab key:

```
.skip-link:focus {
    top: 0;
    z-index: 1;
    width: auto;
    height: auto;
    clip: auto;
}
```

##### Further reading
- [How–to: Use Skip Navigation links](http://a11yproject.com/posts/skip-nav-links/)
- [“Skip Navigation” Links](http://webaim.org/techniques/skipnav/)
- [Fixing “Skip to content” links](https://www.nczonline.net/blog/2013/01/15/fixing-skip-to-content-links/)

#### Default navigation elements

By default, links, buttons, and form items are navigable using the tab key. However, there are times that we may want to include additional items that are tabbable by our users. To do this we can set a “tab index” value to an HTML element:

```
<h3 tabindex="0">This heading is tabbable</h3>
```

The approach should generally be to set a tab index value to zero. A number greater than 1 sets an explicit tab order, and should be avoided.

##### Further Reading

- [Tabindex](http://webaim.org/techniques/keyboard/tabindex)

#### Further Keyboard Accessibility Reading

- [Keyboard Accessibility](http://webaim.org/techniques/keyboard/)
- [Keyboard-Only Navigation for Improved Accessibility](https://www.nngroup.com/articles/keyboard-accessibility)
- [Keyboard Testing Guide](https://pages.18f.gov/accessibility/keyboard/)

### Using a screen reader to navigate the web

For the visually impaired, a screen reader may provide access to our sites and applications. Screen readers also provide a means to test the simplicity of navigation through the application. There are many screen readers available, but for quick testing I recommend [ChromeVox](http://www.chromevox.com/) for the Google Chrome Browser. The ChromeVox screenreader also adds additional focus styles to the active element, which make it possible for those with auditory issues to test screenreader support.

To get started with ChromeVox:

1. Install the [Google Chrome Browser](https://www.google.com/chrome/)
2. Install the [ChromeVox Extension](http://www.chromevox.com/)
3. Follow the [ChromeVox interactive tutorial](http://www.chromevox.com/tutorial/index.html)


#### Other screen readers

Though ChromeVox is great you may want to explore the use of more commonly used screen readers. Here are the most popular screen readers, according to the [WebAIM screen reader survey](http://webaim.org/projects/screenreadersurvey6/).

- [JAWS](http://www.freedomscientific.com/JAWSHQ/JAWSHeadquarters01)
- [ZoomText](http://www.aisquared.com/products/)
- [Window-Eyes](http://www.gwmicro.com/Window-Eyes/)
- [NVDA](http://www.nvaccess.org/)

Additionally, most operating systems ship with built in screen reader support. These can be particularly useful for testing web applications on mobile devices.

- [VoiceOver for Mac](https://www.apple.com/accessibility/osx/voiceover/): CMD + F5 to enable
- [Narrator for Windows](http://windows.microsoft.com/en-us/windows/hear-text-read-aloud-narrator#1TC=windows-8)
- [VoiceOver for iOS](https://www.apple.com/accessibility/ios/voiceover/)
- [Google Talkback](https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback)


## Writing accessible markup

Perhaps the most important aspect of an accessible web application is providing users with semantic HTML, whether it is  delivered server or client side. When writing semantic, well structured HTML we can ensure that our users will receive content that is perceptible to them in a variety of ways.

Here are a few tips for writing semantic and useful HTML:

- Make use of HTML5 content tags such as `<header>`, `<nav>`, `<main>`, `<footer>`, and `<aside>`.
- Mark up the HTML content in the order you would expect the user to read it and use CSS to change the order appearance when necessary.
- Use semantic heading tags that follow a clear outline of page content and avoid using styled paragraphs or other elements as headers.
- Use `<label>` elements to associate the label of form field with its input element.
- Always provide alternate text for images using the alt attribute. When an image is purely decorative, give the alt attribute an empty value (`alt=“”`) so that screen readers know to ignore it.

### ARIA

In addition to writing clear and semantic markup as detailed above, we can make use of ARIA to provide additional guideposts to screen reader users. ARIA stands for Accessible Rich Internet Applications and is a specification designed to make modern web application experiences more accessible. ARIA provides additional attributes that can be added to our markup and provide screen reader users with additional information to describe the role, state, and properties of elements on our page.

Perhaps one of the most immediately useful aspects of ARIA is the use of ARIA roles. ARIA roles allow us to provide specific information to screen readers about the context of HTML elements. Doing this allows screen reader users to quickly navigate to these subsections of our page. I’ve found that watching [these videos](http://zomigi.com/blog/videos-of-screen-readers-using-aria-updated/) of screen readers using ARIA roles to be a really helpful exercise in understanding the usefulness of ARIA.

To use an ARIA role, we add a role attribute to an HTML element and provide it with an ARIA value.

```
<div class=“main-content” role=“main”>
```

There are two categories of ARIA roles that may commonly be used by web application developers:

- Landmark - Landmark roles define content areas that a screen reader user may want to quickly navigate to, such as navigation menus and the main content of the page.
- Widget - Widget roles are used for common interactive UI patterns such as tooltips, tabs, and progress bars.

The [W3C helfpully provides a list](https://www.w3.org/TR/wai-aria/roles#role_definitions) of all of the possible ARIA role definitions. Here are some common ARIA role values that are useful to web application developers:

- application - Content that is declared as a web application rather then a web document.
- banner - Typically the header of the page with the site name.
- search - Indicates a search input.
- main - The main content of the page.
- navigation - Defines any navigation area of the page.
- contentinfo - An area that contains information about the page such as author or organization title and copyright information. This is often the footer.
- group - A collection of UI elements that are not intended to be included in a page summary or table of contents by assistive technologies.
- menu - A list of user choices.
- toolbar - A collection of commonly used functions “represented in a compact visual form.”

ARIA is more than just roles, however. ARIA can be used to define values on progress bars, hidden states, dynamic content updates, and more that are outside of the scope of this introduction. I’ve provided additional links and tutorials in the “further reading” section that detail the usefulness of these additional values.

#### Further reading

- [Notes on Using ARIA in HTML](https://w3c.github.io/aria-in-html/)
- [WAI-ARIA 1.1 Authoring Practices](https://w3c.github.io/aria/practices/aria-practices.html)
- [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA)
- [Getting Started with ARIA](http://a11yproject.com/posts/getting-started-aria/)
- [Quick Tip: Aria Landmark Roles and HTML5 Implicit Mapping](http://a11yproject.com/posts/aria-landmark-roles/)

## Accessibility tools

There are a number of tools that can improve accessibility testing for developers. These allow us to quickly or automatically spot accessibility issues on our sites.

### Browser Extensions and Bookmarklets

Browser extensions and bookmarklets allow us to test the accessibility of a page as we are interacting with it. These are a great option for quickly doing spot checks for things like ARIA role usage, color contrast ratios, descriptive alt text, and form label usage.

Useful browser extensions and bookmarklets:

- [tota11y](https://khan.github.io/tota11y/)
- [WAVE Chrome Extension](http://wave.webaim.org/extension/)
- [Chrome Accessibility Developer Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en)
- [aXe](http://www.deque.com/products/aXe/)

### Command Line Tools

In addition to browser extensions or bookmarklets, we can automate common accessibility checks from the command line. This allows us, as developers, to integrate accessibility checks into our workflow. Typically these tools run our site in a headless browser and test for accessibility concerns such as color contrast, heading order, link content, and alt text.

Useful command line accessibility tools:

- [pa11y](http://pa11y.org/)
- [a11y](https://addyosmani.com/a11y/)
- [node-wcag](https://github.com/cfpb/node-wcag)

### Automating accessibility tests

We can also integrate the above command line tools into an automated build process. Here are a couple of simple examples of how we might do that.

As an npm script in package.json, we could automate the running of accessibility steps with [a11y](https://addyosmani.com/a11y/) against our localhost server.

```javascript
"scripts": {
    "accessibility": "a11y localhost:3000",
  }
```

We could also run those tests as a [Gulp](http://gulpjs.com/) task. This is a simple task that will log the accessibility audit checks and failures to the console.

```javascript
var exec = require('child_process').exec;

gulp.task('accessibility', function (){
  exec('a11y localhost:3000', function(err, stdout, stderr) {
    console.log(stdout);
    console.log(stderr);
  });
});
```

When paired with a continuous integration system, such as [Travis CI](https://travis-ci.com/), we could run these accessibility checks against every build, failing if there are accessibility errors. This would ensure that our codebase remains accessibility compliant when new code is added.

### Accessibility checklists

While we may aim to build our applications with accessibility in mind throughout the development process, it is possible to overlook an accessibility issue. I’ve found it useful in past projects to reference an accessibility checklist prior to launch of a new project. This allows the team I am working with and myself to add a final check for accessibility into the workflow of the project. For a straightforward checklist, I recommend
[The A11Y Project’s Web Accessibility Checklist](http://a11yproject.com/checklist.html), which provides a concise checklist of accessibility best practices. For a more thorough check of WCAG compliance there is [WebAIM's WCAG 2.0 Checklist](http://webaim.org/standards/wcag/checklist). Both of these lists allow you to quickly check for possible accessibility oversights.

## Creating an Accessibility Policy

Adopting an accessibility policy for your project or organization is a way of demonstrating both within and outside of the organization that you are dedicated to accessibility. If an organization is unclear of the value of creating such a policy, the W3C provides [Developing a Web Accessibility Business Case for Your Organization](https://www.w3.org/WAI/bcase/Overview), which clearly outlines the positive outcomes of promoting accessibility.

The majority of national or federal government, state government, and public university web sites offer some form of web accessibility policy. I recommend taking a look at your local and national government sites to see what they are. Additionally a smaller number of corporations and non-profits do the same. I have begun cataloging these policies at [github.com/ascott1/accessibility-policies](https://github.com/ascott1/accessibility-policies).

Here are a few accessibility policies that you may want to explore when developing one for your organization:

- [The Economist](http://www.economist.com/help/accessibilitypolicy)
- [Travelocity](https://www.travelocity.com/p/info-other/web-accessibility-policy)
- [Goodwill Industries](https://www.goodwill.org/uncategorized/accessibility-policy/)
- [Lloyds Bank](https://www.lloydsbank.com/accessibility/policy.asp)
- [Elsevier](https://www.elsevier.com/about/company-information/policies/accessibility)


The W3C provides guidance on [Developing Organizational Policies on Web Accessibility](https://www.w3.org/WAI/impl/pol), complete with a template. I have adapted that template to a more human readable format, in Markdown, which includes a list of commitments:

```
[ORGANIZATION OR PROJECT NAME] is committed to ensuring the accessibility of this site for people with disabilities. We pledge to meet [W3C WAI's Web Content Accessibility Guidelines 2.0](https://www.w3.org/TR/WCAG/), Level AA conformance. Any issues should be reported to [EMAIL ADDRESS].

We are committed to ensuring accessibility through:

- Use of ARIA landmark roles.
- Proper use of HTML headings.
- Perceptible link text and focus states.
- Sufficient color contrast.
- The use of appropriate alt text for images.
- Keyboard navigable forms inputs with descriptive labels.
- Text transcripts for audio and closed captioning for video content.
- Navigation without the need for a mouse or track pad.
```


## In Summary

Accessibility is a core value to ethical web development. By ensuring that our applications are accessible, we are providing access to everyone.

### Additional resources

- [W3C Web Accessibility Initiative](https://www.w3.org/WAI/)
- [W3C Web Accessibility Guidelines](https://www.w3.org/standards/webdesign/accessibility)
- [W3C Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/)
- [The Accessibility Project](http://a11yproject.com/)
- [WebAIM](http://webaim.org/)
- [It’s Tired In Here: Web Accessibility](http://itstiredinhere.com/accessibility/)
