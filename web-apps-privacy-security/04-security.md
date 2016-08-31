# Securing User Data

Early in my web development career I took on a freelance role with a small retail company. Part of the company's business model was catering to corporate clients. Generally, I was doing small site maintenance that involved updating HTML, CSS, and Perl code developed a few years earlier by a (likely more expensive) consulting company. A few days into the job I was familiarizing myself with the codebase when I came across a file named `cc.txt`. This file contained the credit card information of hundreds of corporate clients, stored as plain text. I quickly deleted the file from my local machine and, I'm pretty sure, closed the laptop lid and backed away from the computer slowly. In the end, I advised the company that this needed fixed, told them they should hired someone more experienced than me to do it, and asked that I be let out of the contract. I hope they took that advice.

It seems like every few weeks there's a major breach that leaks user information. Here a few highlights that have been news worthy:

[bulleted list of well known breaches (ashley madison, opm, target, etc)]

These are all from large scale companies and are covered in mainstream media.

It's not all doom and gloom, however. The web is a wonderful place and a reflection of both the positives and negatives of our society. Just as we wouldn't leave our front door wide open when we're not at home, there are steps we can take to lock the doors of our web applications. Taking these steps will help protect the valuable information our users share with us.

---

**ASIDE**

Security is a challenging topic and something that can be explored much more deeply than possible in a single chapter. There are books and entire careers dedicated to this topic. My hope is that this will give you a sound understanding of some basics. The Further Reading section at the end of this chapter contains articles, guides, and books that dive deeper into web security.

---

## Secure User Authentication

- Secure login systems
  - salt & bycrypt
  - OAuth 2.0
  - Two-factor authentication (2FA)
  - Other types of authentication:
    - n-factor
    - one-time passwords
    - biometrics
    - blockchain

## User Sessions

## Encrypting User Data

## Preventing Cross-Site Scripting

## Security Headers

## Tools
  - Chrome Security Panel
  - Code sniffing

## Conclusion

## Further Reading

- [Awesome AppSec](https://github.com/paragonie/awesome-appsec)
- [A practical security guide for web developers ](https://github.com/FallibleInc/security-guide-for-developers/blob/master/README.md)
- [Identity and Data Security for Web Development](http://shop.oreilly.com/product/0636920044376.do) by Jonathan LeBlanc, Tim Messerschmidt
- [Security for Web Developers](http://shop.oreilly.com/product/0636920041429.do) by John Paul Mueller
