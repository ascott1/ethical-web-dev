# Encrypting User Connections with HTTPS

> If only the “controversial” stuff is private, then privacy is itself suspicious. Thus, privacy should be on by default.

— [Tim Bray](https://www.tbray.org/ongoing/When/201x/2012/12/02/HTTPS)

> HTTPS, HTTP over TLS, has been around since 1994, and has been well adopted by the security sensitive web — online banking, shopping, taxes and more. However, the vast majority of websites (est. 81% to 97%) continue to communicate using clear (unencrypted) HTTP — no matter how insecure that is.

  - https://snyk.io/blog/10-reasons-to-use-https/

## How HTTPS Works

At the most basic level, the HTTP request and response cycle is when a web connected computer requests a specific resource through a URL and a server responds with that resource, such as an HTML page.

![HTTP request/response cycle](img/http.png)
(Icons by [unlimicon](https://thenounproject.com/unlimicon/))

When this information is requested, not only are the files sent over the wire, but also a bunch of user information, such as the the user's IP address, location, browser information, system information, and more. More importantly, all of this information is sent as unencrypted plain text over the public internet, meaning that any network sitting between the user's browser and the server has access to that information.  This means that when I request a website, like the graphic above, what I'm really saying is "Hello, I'm user 192.0.0.1 the United States using Mozilla Firefox 48.0.1 on an Intel Macintosh 10.11.6." The server, in turn responds by sending the full resource content unencrypted to the browser.


How HTTPS works...

http://robertheaton.com/2014/03/27/how-does-https-actually-work/
http://computer.howstuffworks.com/encryption4.htm
https://security.stackexchange.com/questions/13688/my-understanding-of-how-https-works-gmail-for-example
https://www.quora.com/How-does-SSL-work



## Why Use HTTPS

## Implementing HTTPS

### Let's Encrypt

https://letsencrypt.org/

https://certbot.eff.org/

#### Renewal

### Other Certificate Options

## Further Reading

- [The United States Government's HTTPS-Only Standard](https://https.cio.gov/)
- [Gov.uk's Using HTTPS](https://www.gov.uk/service-manual/technology/using-https)
- [How Does HTTPS Actually Work?](http://robertheaton.com/2014/03/27/how-does-https-actually-work/) by Rob Heaton
- [We're Deprecating HTTP And It's Going To Be Okay](https://konklone.com/post/were-deprecating-http-and-its-going-to-be-okay) by Eric Mill
