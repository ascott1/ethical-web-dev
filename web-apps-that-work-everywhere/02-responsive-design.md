# Responsive Design

In the early days of the web, through the mid 2000’s, we could safely assume that each user of our site would be accessing it through a computer screen. We spent time researching and considering the typical browser width, but we were safe to assume that our users would be perched in front of a reasonably large screen, with a dedicated keyboard. With the evolution of the smartphone, those assumptions have changed. Users may access our sites quickly, on the go, from a wide range of screen sizes. With the diversity of devices and screens, we can no longer safely make assumptions about the screen size of our users.

The rise of the `.m` site.

http://zurb.com/article/1376/shoppers-don-t-want-your-m-dot-site

Range of screen sizes http://gs.statcounter.com/#all-resolution-ww-monthly-201504-201603-bar

Beyond phones - video game systems, watches, cars, etc.

In 2010, Ethan Marcotte coined the term [Responsive Design](http://alistapart.com/article/responsive-web-design), to describe the practice of building web sites that adapt to a range of screen sizes. 

Responsive Design consists of three core elements:

- **Fluid grids** allow the layout of the screen to condense and expand to fill the screen size, rather than providing a strict width.
- **Flexible media** means that our images and videos are also not limited by a pre-determined width, but an adapt with the content of the page.
- **Media queries** are a CSS technique that allow developers to apply different CSS rules in varying contexts.

By combining these three browser capabilities, we are able to develop sites for a wide range of browser sizes. When we build responsively, we are ensuring that our sites are delivered to our users in a way that works well in the context that they are accessing our site.

## Process

> Responsive design is not about “designing for mobile.” But it’s not about “designing for the desktop,” either. Rather, it’s about adopting a more flexible, device-agnostic approach to designing for the web.

— [Ethan Marcotte](http://unstoppablerobotninja.com/entry/toffee-nosed/)

1. Set the viewport
2. [Device agnostic](http://trentwalton.com/2014/03/10/device-agnostic/) first (instead of mobile first) — baseline experience and enhance up. ([Cutting the mustard](http://responsivenews.co.uk/post/18948466399/cutting-the-mustard))
2. Working with breakpoints
3. Flexible media

## Considerations

Avoid making presumptions about user context

Build for non-ideal conditions

Large click areas
Navigation
Forms