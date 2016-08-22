# Encrypting User Connections with HTTPS

> If only the “controversial” stuff is private, then privacy is itself suspicious. Thus, privacy should be on by default.

— [Tim Bray](https://www.tbray.org/ongoing/When/201x/2012/12/02/HTTPS)

> HTTPS, HTTP over TLS, has been around since 1994, and has been well adopted by the security sensitive web — online banking, shopping, taxes and more. However, the vast majority of websites (est. 81% to 97%) continue to communicate using clear (unencrypted) HTTP — no matter how insecure that is.

  - https://snyk.io/blog/10-reasons-to-use-https/

## How HTTPS Works

At the most basic level, the HTTP request and response cycle is when a web connected computer requests a specific resource through a URL and a server responds with that resource, such as an HTML page.

![HTTP request/response cycle](img/http.png)
(Icons by [unlimicon](https://thenounproject.com/unlimicon/))

When this information is requested, not only are the files sent over the wire, but also a bunch of user information, such as the the user's IP address, location, browser information, system information, and more. More importantly, all of this information is sent as unencrypted plain text over the public internet, meaning that any network sitting between the user's browser and the server has access to that information.  This means that when I request a website, like the graphic above, what I'm really saying is "Hello, I'm user 192.00.000.001 in the United States using Mozilla Firefox 48.0.1 on an Intel Macintosh 10.11.6 and would like the /page.html resource from http://ethicalweb.org." The server, in turn responds by returning the unencrypted resource to the user's browser.

HTTPS works similarly to HTTP, but adds a later of SSL/TLS encryption. This means that requests and responses are made over a secure encrypted connection. These requests only include the user's I.P. address and the domain of the requested resource. In this instance my request would appear as "Hello, I'm user 192.00.000.001 a resource from https://ethicalweb.org." The server would then respond with an encrypted version of the resource.

The United States Government's [https-only standard](https://https.cio.gov/faq/#what-does-https-do?) helpfully demonstrates the difference between these two requests. The standard unencrypted HTTP request includes a number of headers about the client and request:

![Standard HTTP headers](https://https.cio.gov/assets/images/with-http-headers.png)

In contrast the encrypted HTTPS request limits this information:

![HTTPS headers](https://https.cio.gov/assets/images/with-https-headers.png)

### How the SSL/TLS Connection Works

Let's take a closer look at how the SSL/TLS connection works. [briefly explain certificates and keys]

The steps of the process are much like purchasing a car (only a lot faster!):

1. Say hello
3. Exchange the certificate
4. Exchange the keys

First, the user's client says hello by reaching out to the server and requesting the https resource. This request contains all of the information about the user's connection that server will need such as the supported SSL version. In our car metaphor, in this step we've walked in to the dealership and asked to buy a car. We state the type of car we'd like to buy and offered up our trade-in vehicle.

The next step is to exchange the certificate. After the initial client request, the server will respond with a SSL certificate. This certificate has been either self-signed or issued trusted certificate authority and contains information such as name of the domain it is attached to, the name of the certificate owner, dates that the certificate is valid, and a public key. In our car purchase metaphor, this is the deed to the car. With this information, we're able to verify that the seller actually owns the car we're purchasing.

Lastly, the browser and server exchange keys for data encryption and decryption. Along with the certificate, the server sends along a public key. In response, the browser sends the server an encrypted request for the specific URL/assets it is trying to access. The web server then decrypts this information and returns and encrypted version to the client, which then decrypts it locally. In our car purchasing metaphor, we are now handing over the keys to our trade-in, obtaining the key for our new vehicle, and driving away!

All of this happens seamlessly and instantly to a user, but this process adds a the important layer of encrypted protection that HTTPS provides.

<ASIDE>
The keys used in this exchanged are use a symmetric key algorithm, agreed upon between the client and server during the initial connection. Symmetric keys work by using the same key to encrypt and decrypt. To make this process secure, this key is transmitted from the client to server using an asymmetric algorithm (a public/private key exchange), using the server's public key which is contained in the SSL certificate. It's like a double-decker encryption sandwich, ensuring that the information remains secure while traveling between the user and server.
</ASIDE>


## Why Use HTTPS

- confidentiality
- authenticity & integrity
- browsers are deprecating http
- search rankings
- new browser features (like service workers) are only available over https

## Implementing HTTPS

Now that we have looked at how HTTPS works and explored why we should use it, let's take a look at implementing HTTPS for our own sites.

### Let's Encrypt

Perhaps one of the most exciting changes in HTTPS over the past few years is the creation of [Let's Encrypt](https://letsencrypt.org/). Let’s Encrypt is a free, automated, and open certificate authority (CA) created by the [Internet Security Research Group (ISRG)](https://letsencrypt.org/isrg/). The the stated objective of Let's Encrypt is "to make it possible to set up an HTTPS server and have it automatically obtain a browser-trusted certificate, without any human intervention."

[Add more details about how it works? https://letsencrypt.org/how-it-works/]

Though Let's Encrypt provides an open certificate authority, the actual implementation can be challenging. Thankfully many community clients have been created to simplify the implementation process. The most useful, and the one recommended by the Let's Encrypt team, is [certbot](https://certbot.eff.org/). Developed by the [Electronic Frontier Foundation](https://www.eff.org/), certbot works by automatically fetching and deploying Let's Encrypt generated SSL/TLS certificates to our webserver.

The excellent certbot documentation allows us to select a specific webserver and operating system and provides instructions based on these conditions. Let's look at how we would implement certbot on an Apache server running onUbuntu 16.04.

A version of certbot is packaged for 16.04, meaning from our server we can run `apt-get` to install it:

```
$ sudo apt-get install python-letsencrypt-apache
```

Let's Encrypt ships with a beta Apache plugin that will automate obtaining and installing the certificate. To do so, simply run:

```
$ letsencrypt --apache
```

To find guidelines for installation for your server, visit [certbot.eff.org](https://certbot.eff.org).

#### Renewal

Let's Encrypt certificates are valid for 90 days, meaning they will need to be renewed on a regular basis. To do that we could log in to our server every 90 days and run:

```
letsencrypt renew
```

However, this manual process seems like it has a high likelihood of failure (what if we're on vacation, ill, or simply just forget?!). Instead certbot recommends running a cron job that will test for renewal on a daily basis. First let's test the renewal process:

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
17 05,17 * * * letsencrypt renew
```

With this our certificate will automatically renew when needed. 


### Other Certificate Options

- Amazon EC2
- Verisign, Thawte, RapidSSL, etc.

## Conclusion

## Further Reading

- [The United States Government's HTTPS-Only Standard](https://https.cio.gov/)
- [Gov.uk's Using HTTPS](https://www.gov.uk/service-manual/technology/using-https)
- [How Does HTTPS Actually Work?](http://robertheaton.com/2014/03/27/how-does-https-actually-work/) by Rob Heaton
- [We're Deprecating HTTP And It's Going To Be Okay](https://konklone.com/post/were-deprecating-http-and-its-going-to-be-okay) by Eric Mill
