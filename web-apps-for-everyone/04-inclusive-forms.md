# Developing inclusive forms

We forms allow users to interact directly with a site. They are often the thing that separates a web site from a web application.s

## What’s in a name?

In Dale Carnegie’s influential 1936 self-help book, *How To Win Friends and Influence People*, he states “a person's name is, to that person, the sweetest and most important sound in any language.” Names are a core part of our personal identities. We often identify with them, turn at the sound of them said across the room, and intuitively appreciate when a person we have just met understands our names.

Unfortunately, as web developers, it is possible make assumptions about names that lead to their incorrect handling. When working with names, we should be prepared for a variety of characters, spacing, and unique international formats.

In his article [Falsehoods Programmers Believe About Names](Falsehoods Programmers Believe About Names), Patrick McKenzie lists out 40 common misconceptions. Among them, the assumptions that:

> - People have exactly one canonical full name.
> - People’s names fit within a certain defined amount of space.
> - People’s names are written in any single character set.
> - People have last names, family names, or anything else which is shared by folks recognized as their relatives.
> - My system will never have to deal with names from China, Japan, Korea, Ireland, the United Kingdom, the United States, Spain, Mexico, Brazil, Peru, Russia, Sweden, Botswana, South Africa, Trinidad, Haiti, France, or the Klingon Empire, all of which have “weird” naming schemes in common use.

The full list is well worth a read, as it succinctly points out many potential missteps.

In her article, [Hello, My Name is <Error>](http://alistapart.com/article/hello-my-name-is-error), Aimee Gonzalez-Cameron shares her story of taking the GRE, an exam administered for admission to Graduate School in the United States. One of the first instructions in registering for the exam was as follows:

> Important: The name you use when you register for a GRE test must exactly match (excluding accents, apostrophes and spaces) the name on the identification (ID) documents that you will present on the day of your GRE test. If it does not, you may be prohibited from taking the test or your test scores may be canceled after you take the test. For example, a last name of Fernandez de Córdova would be entered as FernandezdeCordova.

As she points out, “Students shouldn’t stress about instructions or worry that their answers will be thrown out because they can’t complete the first step correctly.” The lack of a technical system that properly handles a common American surname format is both culturally insensitive and requires extra instruction for correct handling. 

Perhaps relatable from the perspective of many developers is the case of Christopher Null. Without reading further, you may already be shaking your head at the heartache that a last name of “Null” may cause when dealing with web forms. In his article, [Hello, I’m Mr. Null. My Name Makes Me Invisible to Computers](http://www.wired.com/2015/11/null/), he details his experience using the web with the last name of Null. Since “null” is used to represent an empty string in the majority of programming languages, it is sometimes used to check for blank form fields. Because of this, many form fields will assume the field is blank, report an error, or crash, forcing him to use a different last name.

As developers, we can take a more inclusive strategy to working with names, treating these not as edge cases, but instead by expecting a wide variety of potential inputs.

### International names

Names come in many different formats around the world, however it is easy to apply our own cultural biases when designing systems that deal with names. As an American, for instance, my bias is to consider names in the format of a first name followed by a surname. Based on that format I make several, potentially false assumptions, about things such as familial relationship. However, there are many different ways that a name can be constructed even with a single country or culture. Let’s look at a few of these structures to see how they may challenge our assumptions.

### Chinese

> Modern Chinese names consist of a surname known as xing (Chinese: 姓; pinyin: xìng), which comes first and is usually monosyllabic, but not always, followed by a personal name called ming (Chinese: 名; pinyin: míng), 

> Chinese people, except for those traveling or living outside of China, rarely reverse their names to the western naming order (given name, then family name). 

### Icelandic names
> Icelandic names differ from most current Western family name systems by being patronymic (occasionally matronymic): they reflect the father (or mother) of the child and not the historic family lineage. 

> Lists of names are not always sorted by family name around the world. For example, Thai and Icelandic people expect lists to be sorted by given name instead.

 Jón Birgisson
 
Jón “Birgi’s son”
 
 Sigrún Jónsdóttir
 
Sigrún “Jon’s daughter”

### Malaysian names

### Arabic names

> Arabic names were historically based on a long naming system; most Arabs did not simply have given/middle/family names, but a full chain of names.

https://en.wikipedia.org/wiki/Arabic_name

> With "Abdul": Arabic names may be written "Abdul (something)", but "Abdul" means "servant of the" and is not, by itself, a name. Thus for example, to address Abdul Rahman bin Omar al-Ahmad by his given name, one says "Abdul Rahman", not merely "Abdul". If he introduces himself as "Abdul Rahman" (which means "the servant of the Merciful"), one does not say "Mr. Rahman" (as "Rahman" is not a family name but part of his (theophoric) personal name); instead it would be Mr. al-Ahmad, the latter being the family name.

### Indian

### Portugese

> A Portuguese name is typically composed of one or two given names, and a number of family names (rarely one, but often two or three, seldom more). The first surname(s) are usually the mother's family surname(s) and the final surname(s) are the father's family surname(s).

Sofia Matilde Almeida Pais
António Borges Santos

### Russian names

First name, patronymic name, surname:

Romanized: Yelе́na Savvichna Razumovsky
Cyrillic: Еле́на Саввична Разумовский

Double surnames are allowed, but are rare

### Irish names

Francis O'Neill

### Spanish names


These are only a few examples of how names may differ around the world. The W3C’s article [Personal names around the world](https://www.w3.org/International/questions/qa-personal-names) dives into greater detail and links to several additional Wikipedia articles discussing naming formats. 

### Mojibake

[Mojibake](https://en.wikipedia.org/wiki/Mojibake) is a term used to describe the garbled set of characters that are produced through an improper use of character encoding. Mojibake is typically caused by text that lacks proper (or any) Unicode encoding. When a user’s name contains special characters it may not be uncommon for them to often see mojibake versions of their name. A quick Twitter image search results for mojibake reveals many encoding issues across the web, though it is likely that the majority go undocumented or are documented without knowing the term.

In his talk, [Hello, my name is __________.](http://patch.codes/talks/hello-my-name-is/), developer Nova Patch surfaced several examples of Mojibake affecting users of web services. Perhaps the most well documented and consistent mojibake mangling of a name belongs to Nóirín Plunkett, who shared several instances of their mojibaked named on Twitter[^1].

![image OF Nóirín’s tweets displaying mojibake](img/mojibake-tweets.png)

<aside>
Through the research of this book, I discovered that Nóirín Plunkett passed away in July 2015. Nóirín was an invaluable part of the open source community and an advocate for good in the world of software development. Both the [Apache Foundation](https://www.apache.org/memorials/noirin.html) and [Ada Initiative](http://adainitiative.org/2015/07/29/remembering-noirin-plunkett/) have offered heartfelt tributes to Nóirín.
</aside>

Perhaps one of the more impressive mojibake instances, was of a Russian postal worker who hand [corrected a package’s mojibake](http://text-mode.tumblr.com/post/31409503070/russian-postmen-fix-an-error-caused-by-an). This illustrates how common encoding problems can be when working with Cyrillic languages. In fact, there is even a Russian specific term for mojibake, krakozyabrı. 

![image of hand decoded mojibake](img/russian-post.jpg)

(Image via http://text-mode.tumblr.com/)

[1]: Here are the Tweets referenced in the image:
- https://twitter.com/noirinp/status/77745010547769344
- https://twitter.com/noirinp/status/151004631818977281
- https://twitter.com/noirinp/status/162264316203114498
- https://twitter.com/noirinp/status/394893223145271296
- https://twitter.com/noirinp/status/600750084410642432

### Unicode

[No Such Thing as Plain Text](https://www.cqse.eu/en/blog/no-such-thing-as-plain-text/)

[The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets](http://www.joelonsoftware.com/articles/Unicode.html)


If possible include a single text input and don’t use names as the unique identifier. Allow the input field to take in long names and if possible avoid limiting the length of the field in your database.

“What should we call you?”

If splitting *must* occur, use more inclusive language such as “family name” and “other/given names.”

Legal names flowchart? https://twitter.com/duckinator/status/545934151610675200

Allow punctuation such as hyphens, apostrophes, etc. and spaces in names

## Inclusive gender

Facebook & Google’s patterns!

http://www.yoomee.com/how-to-ask-about-gender

http://www.lgbt.cusu.cam.ac.uk/campaigns/think/forms/


http://www.formulate.com.au/blog/sex-and-gender


## Further Reading

- [Hello, I’m Mr. Null. My Name Makes Me Invisible to Computers](http://www.wired.com/2015/11/null/)
- [Hello, my name is __________.](http://patch.codes/talks/hello-my-name-is/)
- [Falsehoods Programmers Believe About Names](http://www.kalzumeus.com/2010/06/17/falsehoods-programmers-believe-about-names/)
- [Personal names around the world](https://www.w3.org/International/questions/qa-personal-names)
- [Hello, My Name is <Error>](http://alistapart.com/article/hello-my-name-is-error)
- [Personal Histories](http://www.sarawb.com/2015/01/13/personal-histories/)

