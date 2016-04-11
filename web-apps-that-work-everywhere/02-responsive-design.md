# Responsive Design

For more than a decade of the web’s existence, we could safely assume that each user of our site would be accessing it through a computer screen. Despite this, early websites were, by default, adaptive to a variety of screen sizes. The web’s first site, Tim Berners-Lee’s [World Wide Web](http://info.cern.ch/hypertext/WWW/TheProject.html), works beautifully at a range of  screen sizes.

[SCREENSHOT OF WWW AT SMALLER SIZE]

Despite this, we spent time researching and considering the typical browser width and assumed that our users would be perched in front of a reasonably large screen, with a dedicated keyboard. With the evolution of the smartphone, those assumptions have changed. Users may access our sites quickly, on the go, from a wide range of screen sizes. With the diversity of devices and screens, we can no longer safely make assumptions about the screen size of our users.

The initial reaction to the rise of smartphones was to create dedicated mobile versions of our sites. This often sat on a `.m` subdomain and provided a mobile optimized experience. At first, this seemed like a great solution as it allowed users to access our services in a format that was streamlined for their device. For developers, this also meant maintaining multiple codebases. For users, this often meant dealing with a limited subset of functionality when using a mobile device.  

Today, the number of devices that connect to the web is again expanding. Users may access our applications from a desktop computer, a mobile phone, a tablet, a reading device, a watch, a video game system, or in their car. 

Range of screen sizes http://gs.statcounter.com/#all-resolution-ww-monthly-201503-201604

In 2010, Ethan Marcotte coined the term [Responsive Design](http://alistapart.com/article/responsive-web-design), to describe the practice of building web sites that adapt to a range of screen sizes. By building responsively, we can develop a single codebase that acclimates to the screen size of the device being used by the user. This allows us to make fewer assumptions while delivering a site that works in any context.

Responsive design consists of three core elements:

- **Fluid grids** allow the layout of the screen to condense and expand to fill the screen size, rather than providing a strict width.
- **Flexible media** means that our images and videos are also not limited by a pre-determined width, but an adapt with the content of the page.
- **Media queries** are a CSS technique that allow developers to apply different CSS rules in varying contexts.

By combining these three browser capabilities, we are able to develop sites for a wide range of browser sizes. When we build responsively, we are ensuring that our sites are delivered to our users in a way that works well in the context that they are accessing our site.

## Process

> Responsive design is not about “designing for mobile.” But it’s not about “designing for the desktop,” either. Rather, it’s about adopting a more flexible, device-agnostic approach to designing for the web.

— [Ethan Marcotte](http://unstoppablerobotninja.com/entry/toffee-nosed/)

The process of responsive design can be broken down into four steps.

1. Set the browser viewport to adapt to the screen size.
2. Set flexible media elements that can adapt to the width of the container.
3. Develop a [device agnostic](http://trentwalton.com/2014/03/10/device-agnostic/) baseline experience.
4. Using CSS3 media queries, enhance the experience at a variety of screen sizes (often termed “break points”).

Let’s tease this process apart by creating a very simple responsive page.

[Cutting the mustard](http://responsivenews.co.uk/post/18948466399/cutting-the-mustard)


### Note: CSS Frameworks

If you are not a fan of writing CSS (and who could blame you?), you may opt to use a CSS framework such as [Bootstrap](https://getbootstrap.com/) or [Foundation](http://foundation.zurb.com/). These and many other UI frameworks are responsive by default and can be useful for rapid prototyping and quick interface development.

## Considerations

Avoid making presumptions about user context

Build for non-ideal conditions

Large click areas
Navigation
Forms


## Further Reading