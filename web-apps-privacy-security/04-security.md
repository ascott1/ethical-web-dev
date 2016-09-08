# Securing User Data

Early in my web development career I took on a freelance role with a small retail company. Part of the company's business model was catering to corporate clients. Generally, I was doing small site maintenance that involved updating HTML, CSS, and Perl code developed a few years earlier by a (likely more expensive) consulting company. A few days into the job I was familiarizing myself with the codebase when I came across a file named `cc.txt`. This file contained the credit card information of hundreds of corporate clients, stored as plain text. I quickly deleted the file from my local machine and, I'm pretty sure, closed the laptop lid and backed away from the computer slowly. In the end, I advised the company that this needed fixed, told them they should hired someone more experienced than me to do it, and asked that I be let out of the contract. I hope they took that advice.

It seems like every few weeks there's a major breach that leaks user information. Brian Krebs does a good job of cataloging major breaches on his site [krebsonsecurity.com](http://krebsonsecurity.com/category/data-breaches/). Here a few highlights that have been heavily covered by the news media:

- In 2015 it was uncovered that the United States Government's Office of Personnel Management (OPM) had undergone a data breach containing millions of government employee records. These records included security clearance information, personal fingerprints, and fingerprints. [^1: https://en.wikipedia.org/wiki/Office_of_Personnel_Management_data_breach]
- The extramarital dating website, Ashley Madison, was infamously breached in 2015. Revealing user information such as names, addresses, email addresses, and phone numbers. [^2: https://www.wired.com/2015/08/happened-hackers-posted-stolen-ashley-madison-data/]
- In 2015 the insurance provider Anthem Inc. was breached. In this breach hackers stole over 78 million records containing names, birthdays, medical IDs, social security numbers, street addresses, e-mail addresses and employment information [^3: https://en.wikipedia.org/wiki/Anthem_medical_data_breach].
- In 2016 the professional social network LinkedIn announced that they had been breached in 2012 and that hackers had released a data set containing over 100 million user email addresses and hashed passwords. [^4: https://blog.linkedin.com/2016/05/18/protecting-our-members]
- In 2016 the file syncing service Dropbox also announced a 2012 breach, which included account information for over 60 million of its users. [^5: https://motherboard.vice.com/read/hackers-stole-over-60-million-dropbox-accounts]

It's not all doom and gloom, however. The web is a wonderful place and a reflection of both the positives and negatives of our society. Just as we wouldn't leave our front door wide open when we're not at home, there are steps we can take to lock the doors of our web applications. Taking these steps will help protect the valuable information our users share with us. In this chapter we'll explore the basics of web development security.

---

**ASIDE**

Security is a challenging topic and something that can (and should!) be explored much more deeply than possible in a single chapter. There are books and entire careers dedicated to this topic. My hope is that this chapter will give you a high-level overview of the basics. The Further Reading section at the end of this chapter contains articles, guides, and books that dive deeper into web security.

---

## Build On A Strong Foundation

Being a web developer means that we are constantly learning about and using new tools. It's an exciting perk of the job. That said, when building secure applications we are often best-served to use established frameworks that have been thoroughly vetted and that provide baked-in security support. As an example, let's look at the security options when building a web application with Python or Node.js.

The Python environment is relatively stable and most web applications are built using either the [Django](https://www.djangoproject.com/) or [Flask](http://flask.pocoo.org/) web frameworks. Django provides [many security features out of the box](https://docs.djangoproject.com/en/1.10/topics/security/), such as cross site scripting, SQL injection, and clickjacking protection. As Flask is an intentionally more lightweight framework, it comes with a few [built-in security features](http://flask.pocoo.org/docs/0.10/security/), such as lightweight cross site scripting protection. Additional security features can be added with the [Flask-Security](https://pythonhosted.org/Flask-Security/) extension.

Node.js is notorious for it's rate of change and the number of frameworks and libraries available to developers. It can be both something to love about the platform as well as a frustation point for many developers. The site [Node Frameworks](http://nodeframework.com/) attempts to catalog them all. Despite there being dozens of Node.js web framework options, when considering security we are likely to be best-served by choosing an established framework that is used in production by other web applications, such as [Express](http://expressjs.com/).

Similar to Flask, Express is a lightweight application framework, but there are several plugins that enhance its security features. The two most common plugins are [Lusca](https://github.com/krakenjs/lusca), which was developed by PayPal, and [Helmet](https://github.com/helmetjs/helmet). These both add sensible defaults for features such as cross-site scripting protection, cross-site request forgery protection, content security policy settings, and more.

In addition to using security focused libraries, we should also work to ensure that our dependencies are up to date and free of known vulnerabilities.

In Python we can check for outdated pip installed packages with:

```
pip list --outdated
```

Similarly in Node.js we can list outdated packages with npm:

```
npm outdated
```

In addition to these manual methods there are tools that will help maintain dependency updates and scan for security vulnerabilities. [Greenkeeper](https://greenkeeper.io) is a tool which will scan your project for outdated Node.js dependencies and will create a pull request with the updates. Greenkeeper will also run your application's test suite, ensuring that the updated dependency does not break the build. [Snyk](https://snyk.io/) is a tool that will scan Node.js packages for known vulnerabilities and alert you to insecure dependencies. The site also provides a command line tool for fixing these vulnerabilities.

Though these examples are limited to Python and Node.js, I hope that you can see how the concepts map to your web stack of choice. When we use established technologies and utilize built-in or plugin-based security features, we are creating a solid security foundation for our site.

## OWASP Top 10

Now that we've started our application off on a strong foundation, it's worth exploring the common security vulnerabilities that we should be aware of. Every few years the Open Web Application Security Project (OWASP) publishes a [list of the most critical web application security flaws](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project). Being aware of this list of common vulnerabilities can provide us with an awareness of potential weaknesses in our own applications.

1. Injection
2. Broken authentication and session management
3. Cross-site scripting
4. Insecure direct object reference
5. Security misconfiguration
6. Sensitive data exposure
7. Missing function level access control
8. Cross-site request forgery
9. Using components with known vulnerabilities
10. Unvalidated redirects and forwards

## Secure User Authentication

### Creating Secure Login Systems
  - salt & bycrypt
  - OAuth 2.0
  - Two-factor authentication (2FA)

### Password Strength

https://blogs.dropbox.com/tech/2012/04/zxcvbn-realistic-password-strength-estimation/

---

**ASIDE**

The least secure part of any login system is the human using it. Weak and shared passwords, phishing, etc.

---

### Other types of authentication:
    - n-factor
    - one-time passwords
    - biometrics
    - blockchain


### User Sessions

## Encrypting User Data

## Sanitizing Data

## Security Headers

## Bug Bounty Programs and Security Disclosures

https://titanous.com/posts/security-disclosure-policy-best-practices

https://bounty.github.com/

## Additional Tools
  - Chrome Security Panel
  - Code sniffing

## Conclusion

## Further Reading

- [Awesome AppSec](https://github.com/paragonie/awesome-appsec)
- [A practical security guide for web developers ](https://github.com/FallibleInc/security-guide-for-developers/blob/master/README.md)
- [Python & Django Security on a Shoestring: Resources](http://nerd.kelseyinnis.com/blog/2016/05/30/python-django-security-on-a-shoestring-resources/) by Kelsey Gilmore-Innis
- [Mozilla Cybersecurity Delphi 1.0: Towards a user-centric policy framework](https://blog.mozilla.org/netpolicy/files/2015/07/Mozilla-Cybersecurity-Delphi-1.0.pdf)
- [Identity and Data Security for Web Development](http://shop.oreilly.com/product/0636920044376.do) by Jonathan LeBlanc, Tim Messerschmidt
- [Security for Web Developers](http://shop.oreilly.com/product/0636920041429.do) by John Paul Mueller
