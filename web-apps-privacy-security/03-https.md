# Encrypting User Connections with HTTPS

The letter S is the 19th letter of the alphabet, but when appended to HTTP signifies an added state of security. HTTPS was first developed for use in Netscape Navigator in 1994[^1] and became an important indicator of security for e-commerce and banking sites on the developing web. As we move an ever increasing amount of personal data and information across the web, ensuring user privacy and the authenticity of information become increasingly important.

Over a standard HTTP connection, users are open to advertising injection, content changes, and additional tracking that isn't possible over HTTPS. This is both bad for users and takes away control from site owners. Because of this, there has been a movement towards building HTTPS-only sites. Despite this, less than 11% of the top million websites currently use HTTPS by default[^2].

In this chapter, we'll explore how HTTPS works, investigate the benefits of HTTPS-only sites, and look at how we can enable HTTPS for our sites today.

[^1]: https://books.google.com/books?id=FLvsis4_QhEC&pg=PA344&hl=en#v=onepage&q&f=false
[^2]: https://trends.builtwith.com/ssl/SSL-by-Default

## How HTTPS Works

At the most basic level, the HTTP request and response cycle is when a web connected computer requests a specific resource through a URL and a server responds with that resource, such as an HTML page.

![HTTP request/response cycle](img/http.png)
(Icons by [unlimicon](https://thenounproject.com/unlimicon/))

When this information is requested, not only are the files sent over the wire, but so user information, such as the the user's IP address, location, browser information, system information, and more. More importantly, all of this information is sent as unencrypted plain text over the public internet, meaning that any network sitting between the user's browser and the server has access to that information. This means that when I request a website, like the graphic above, what I'm really saying is "Hello, I'm user 192.00.000.001 in the United States using Mozilla Firefox 48.0.1 on an Intel Macintosh 10.11.6 and would like the `/page.html` resource from http://ethicalweb.org." The server, in turn responds by returning the unencrypted resource to the user's browser.

HTTPS works similarly to HTTP, but adds a layer of SSL(Secure Sockets Layer)/ TLS(Transport Layer Security) encryption. This means that requests and responses are made over a secure encrypted connection. These requests only include the user's I.P. address and the domain of the requested resource. In this instance my request would appear as "Hello, I'm user 192.00.000.001 and would like a resource from https://ethicalweb.org." The server would then respond with an encrypted version of the resource.

---

**ASIDE**
TLS is the updated and more secure version of SSL. Throughout the remainder of the chapter, I will refer to SSL/TLS simply as TLS, though some external references may use SSL as the catch-all term. Confusing? Yup! This represents one of the many reasons that HTTPS can seem intimidating.

---

The United States Government's [https-only standard](https://https.cio.gov/faq/#what-does-https-do?) helpfully demonstrates the difference between these two requests. The standard unencrypted HTTP request includes a number of headers about the client and request:

![Standard HTTP headers](https://https.cio.gov/assets/images/with-http-headers.png)

In contrast the encrypted HTTPS request limits this information:

![HTTPS headers](https://https.cio.gov/assets/images/with-https-headers.png)

### How the TLS Connection Works

Let's take a closer look at how the TLS connection works. To provide an encrypted connection, a site must obtain a TLS certificate. TLS certificates are used to verify the authenticity of the domain, relay information about the certificate itself, and contain a public key that will be exchanged with the user's browser.

The steps of the process are much like purchasing a car (only a lot faster!):

1. Greet one another
2. Exchange the certificate
3. Exchange the keys

First, the user's client says hello by reaching out to the server and requesting the https resource. This request contains all of the information about the user's connection that the server will need, such as the supported TLS version. In our car metaphor, in this step we've walked in to the dealership and asked to buy a car, we state the type of car we'd like to buy, and offered up our trade-in vehicle.

The next step is to exchange the certificate. After the initial client request, the server will respond with a TLS certificate. This certificate has been either self-signed or issued by a trusted certificate authority and contains information such as name of the domain it is attached to, the name of the certificate owner, dates that the certificate is valid, and a public key. In our car purchase metaphor, this is the deed to the car. With this information, we're able to verify that the seller actually owns the car we're purchasing.

Lastly, the browser and server exchange keys for data encryption and decryption. Along with the certificate, the server sends along a public key. In response, the browser sends the server an encrypted request for the specific URL/assets it is trying to access. The web server then decrypts this information and returns an encrypted version to the client, which then decrypts it locally. In our car purchasing metaphor, we are now handing over the keys to our trade-in, obtaining the key for our new vehicle, and driving away!

All of this happens seamlessly and instantly to a user, but this process adds a the important layer of encrypted protection that HTTPS provides.

---

**ASIDE**
The keys used in this exchanged are use a symmetric key algorithm, agreed upon between the client and server during the initial connection. Symmetric keys work by using the same key to encrypt and decrypt. To make this process secure, this key is transmitted from the client to server using an asymmetric algorithm (a public/private key exchange), using the server's public key which is contained in the TLS certificate. It's like a double-decker encryption sandwich, ensuring that the information remains secure while traveling between the user and server.

---

## Why Use HTTPS

As we looked at what HTTPS is and how it works, we can begin to see some of the value it provides to our users as well as ourselves as site owners and maintainers. Specifically HTTPS is important for:

- User privacy and security
- Site authenticity & integrity
- Browser deprecated HTTP
- Potential search ranking improvements

Let's take a closer look at each of these.

### User Privacy and Security

In the previous chapter we looked at the value we can provide by respecting a user's privacy with Do Not Track. However, many users are simply unaware of these types of features. One way that we can aid the privacy of all users is by using HTTPS on our sites. This provides our users with private, encrypted connections to our sites. HTTPS prevents monitoring of sites on public networks as well as preventing passive attackers from eavesdropping on a user's web traffic.

### Site Authenticity

HTTPS aids in verifying the authenticity of a site and its content. When a site is served over HTTPS a user can feel confident that they are visiting the site they intended and that its content is what the site owner had intended for the user.

When describing the decision to move to HTTPS, popular news website BuzzFeed detailed the [authenticity benefits of HTTPS](https://www.buzzfeed.com/jasonreich/buzzfeed-and-https):

> Verification is a lesser known, but equally important benefit of HTTPS. It helps prevent what is called a Man-in-the-Middle attack, or MITM attack. An MITM attack via your browser can change the content of any non-HTTPS website you’re visiting without you knowing. This means an attacker can [modify news stories](http://newstweek.com/2011-01-07-device-distorts-news-on-wireless-neworks) to change or remove info, or they can change the contact details on a BuzzFeed contributor’s author page so you see a fake account the attacker controls.


### Browser Deprecated HTTP

Currently, browsers display an indication whenever a site is being served securely using HTTPS. This appears as a green padlock next to the site's URL:

![](img/https-url-example.png)

However, there is a lack of indicator for browsers that are not using HTTPS:

![](img/no-https-url-example.png)

Recently the Chromium team pointed out that "people do not generally perceive the absence of a warning sign" and consequently suggested that browsers instead [mark HTTP as insecure](https://www.chromium.org/Home/chromium-security/marking-http-as-non-secure), alerting users that sites served over HTTP.

#### New Browser Features

The second way that browsers are deprecating HTTP is by making new browser APIs available only to sites server over HTTPS. These include offline capabilities with service workers (covered in [Building Web Apps that Work Everywhere](http://www.oreilly.com/web-platform/free/building-web-apps-that-work-everywhere.csp), the ability to access user camera and audio with getUserMedia, and user location information with the geolocation API. Looking at the types of information these APIs will have access to, I'm thankful that browser vendors have decided that they should only be accessed over a secure connection. As and added benefit, as we develop forward-thinking applications, HTTPS will quickly become a requirement.

### Improved search rankings

In 2014 Google announced that the search engine would begin to prioritize sites using HTTPS in search results. According to the [blog post announcement](https://security.googleblog.com/2014/08/https-as-ranking-signal_6.html):

> [O]ver the past few months we’ve been running tests taking into account whether sites use secure, encrypted connections as a signal in our search ranking algorithms. We’ve seen positive results, so we’re starting to use HTTPS as a ranking signal. For now it's only a very lightweight signal—affecting fewer than 1% of global queries, and carrying less weight than other signals such as high-quality content—while we give webmasters time to switch to HTTPS. But over time, we may decide to strengthen it, because we’d like to encourage all website owners to switch from HTTP to HTTPS to keep everyone safe on the web.

If non-technical colleagues or clients are not yet convinced on the need for HTTPS everywhere, the potential for improved search rankings may serve as an additional selling point.

## Implementing HTTPS

Now that we have looked at how HTTPS works and explored why we should use it, let's take a look at implementing HTTPS for our own sites.

### Let's Encrypt

Perhaps one of the most exciting changes in HTTPS over the past few years is the creation of [Let's Encrypt](https://letsencrypt.org/). Let’s Encrypt is a free, automated, and open certificate authority (CA) created by the [Internet Security Research Group (ISRG)](https://letsencrypt.org/isrg/). The stated objective of Let's Encrypt is "to make it possible to set up an HTTPS server and have it automatically obtain a browser-trusted certificate, without any human intervention."

Though Let's Encrypt provides an open certificate authority, the actual implementation can be challenging. Thankfully many community clients have been created to simplify the implementation process. The most useful, and the one recommended by the Let's Encrypt team, is [Certbot](https://certbot.eff.org/). Developed by the [Electronic Frontier Foundation](https://www.eff.org/), Certbot works by automatically fetching and deploying Let's Encrypt generated TLS certificates to our server.

The excellent Certbot documentation allows us to select a specific server and operating system and provides instructions based on these conditions. Let's look at how we would implement Certbot on an Apache server running on Ubuntu 16.04.

A version of Certbot is packaged for 16.04, meaning from our server we can run `apt-get` to install it:

```
$ sudo apt-get install python-letsencrypt-apache
```

Let's Encrypt ships with a beta Apache plugin that will automate obtaining and installing the certificate. To do so, simply run:

```
$ letsencrypt --apache
```

And that's it! With those few simple commands we will have installed a TLS certificate for our server. To find guidelines for installation for your specific server configuration, visit [certbot.eff.org](https://certbot.eff.org).

#### Renewal

Let's Encrypt certificates are valid for 90 days, meaning they will need to be renewed on a regular basis. To do that we could log in to our server every 90 days and run:

```
letsencrypt renew
```

However, this manual process seems like it has a high likelihood of failure (what if we're on vacation, ill, or simply just forget?!). Instead Certbot recommends running a cron job that will test for renewal on a daily basis. First let's test the renewal process:

```
$ letsencrypt renew --dry-run
```

Once we've verified that this works, we can create the cron job. We'll create a job that runs the renew script twice daily at 5:17am and 5:17pm (certbot requests that the jobs run at a random minute within the hour).

First open the `crontab`:

```
crontab -e
```

Then add the following to the file:

```
17 05, 17 17 * * * letsencrypt renew
```

With this our Let's Encrypt issued certificate will automatically renew when needed.


### Other Certificate Options

Though Let's Encrypt is a fantastic and recommended option, it may not be the right one for you or your organization. If you are using Amazon Web Services, they now offer [free TLS certificates](https://aws.amazon.com/certificate-manager) that are very easy to set up and deploy. I have used this service and it is a great and simple option. Another option, [SSLMate](https://sslmate.com/), works similarly to Let's Encrypt by automating certificates, but is not free.

For some it may also be preferable to go the traditional route of purchasing the certificate from a Certificate Authority (CA) and uploading it to the server. Common TLS CA's are [Verisign](https://www.verisign.com/), [Thawte](https://www.thawte.com/), and [RapidSSL](https://www.rapidssl.com/).

When implementing TLS on your server, Mozilla provides an [Configuration Generator](https://mozilla.github.io/server-side-tls/ssl-config-generator/). This easily outputs the configuration needed for popular servers such as Apache, Nginx, and Lighttpd with a variety of TLS certificate types. Once configured, SSL Labs provides a [SSL Server Test](https://www.ssllabs.com/ssltest/), which allows us analyze the TLS configuration of our server.

## Other Considerations

Once we have implemented HTTPS, there are a few site-wide changes to take into consideration:

- Redirecting HTTP to HTTPS
- Enabling HTTP Strict Transport Security
- Preventing mixed content and using relative URLs
- Using secure cookies

## Redirect HTTP to HTTPS

If we add HTTPS to an existing site, it may be worth redirecting all HTTP requests to HTTPS. This will ensure that all existing external links are served over a secure connection.

Following our previous Let's Encrypt example, we could redirect all links with Apache by adding the following to our Virtual Host:

```
  ServerName www.example.com
  Redirect "/" "https://www.example.com/"
```


## HTTP Strict Transport Security

When forwarding HTTP to HTTPS, the user is initially opening a request with the unencrypted version of our site before being redirected. This does open users up to a man in the middle attack. To prevent this from happening on future visits, we can pair the forward with HTTP Strict Transport Security, to ensure that users only access the site over HTTPS.

HTTP Strict Transport Security (HSTS) is a browser feature that allows a site to request that it only be served over HTTPS on future visits. This works by a server providing a `Strict-Transport-Security` along with a max-age. Once receiving this header, the browser will only request pages from that domain over HTTPS.

Here is the HSTS header, along with an expiration of on year, and instructions to include sub domains:

```
Strict-Transport-Security: max-age=31536000; includeSubDomains
```

To set the HSTS header in Apache, we would add the following to our Virtual Host:

```
Header always set Strict-Transport-Security "max-age=63072000; includeSubdomains; preload"
```


## Mixed Content and Relative URLs

Mixed occurs when a site is served over a secure HTTPS connection, but contains links to resources such as images, CSS, or JavaScript that is served over HTTP. When this occurs, browsers display an error message to users, warning them that the site contains insecure content.  

This often happens in error or may occur when a site is converted to HTTPS and has lingering absolute links. To avoid this situation, convert links beginning with `http://` to `https://` or use relative URLs when linking to local files.


### Secure cookies

When sending cookies form our server application over an HTTPS connection, we should enable the `secure` flag. Using the `secure` flag will ensure that the cookie request only be sent over an encrypted connection (HTTPS).

For example, when setting a cookie using the popular Express.js web framework, `secure` is a simple added parameter:

```
res.cookie('user', 'adam', { secure: true });
```

## Conclusion

HTTPS provides numerous benefits to both site owners and users and helps to make the web more secure. Whatever the method you choose to implement HTTPS for your sites, you are taking important steps to improve the security and privacy of your users.

## Further Reading

- [The United States Government's HTTPS-Only Standard](https://https.cio.gov/)
- [Gov.uk's Using HTTPS](https://www.gov.uk/service-manual/technology/using-https)
- [How Does HTTPS Actually Work?](http://robertheaton.com/2014/03/27/how-does-https-actually-work/) by Rob Heaton
- [Is TLS Fast Yet?](https://istlsfastyet.com/)
- [Securing the Web](https://www.w3.org/2001/tag/doc/web-https), W3C report
- [Encrypting data in transit](https://developers.google.com/web/fundamentals/security/encrypt-in-transit/), Google Developers resource
- [We're Deprecating HTTP And It's Going To Be Okay](https://konklone.com/post/were-deprecating-http-and-its-going-to-be-okay) by Eric Mill
