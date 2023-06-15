---
title: Web Skimmers
description: Explaining Web Skimmers
date: '2023-6-13'
author: Paris Saucedo 
categories: 
 - Phishing Scams 
 - Blog Post 
published: true
---

# Table of Contents


# What are Web Skimmers ?
![enter image description here](https://media.kasperskycontenthub.com/wp-content/uploads/sites/103/2019/10/28095137/magecart.jpg)

**Web skimmers are a type of malware that operates by adding a small piece of code onto a legitimate website to exfiltrate private information, including credit card information and social security numbers, to an attacker's server, while continuing to submit the details to the legitimate site. Because of the way they are made, web skimmers are impossible to detect just by looking at the web page since they operate entirely in the background and have no obvious indicators.** 


## Origins ? 

**Web skimmer or JavaScript skimmer attacks are also called form jacking or Magecart attacks, owing to the fact that they were first widely identified in use on sites running the Magento software**.

**Web skimmers take their name from ATM skimmers, where a criminal will place counterfeit hardware onto real cash machines to steal credit card information, similar to the injected code of a web skimmer sending sensitive consumer information to an attacker's server.** 

![enter image description here](https://i.imgur.com/kS3bRP7.png)

Web skimmers started to enter the public eye in 2018 after a series of high-profile attacks on major retailers became known. Subjects of these attacks included British Airways, Newegg, and Ticketmaster. The British Airways attack alone had an estimate of up to 380,000 consumers that had their private information stolen.  


## Statistics

#### From source: [A Closer Look at the Web Skimmer](https://unit42.paloaltonetworks.com/web-skimmer/)
The following statistics were gained using WildFire, a cloud-based malware protection engine. It detected that 351,972 HTML pages were compromised by skimmer malware from October 2019-October 2020. These samples belong to 6,684 unique domain names.
  
When deriving the geographical locations for the domain names to generate a heat map as shown below in Figure 1. This heat map indicates that the majority of the domain names are located in the United States. 

![heatmapofwebskimmers](https://unit42.paloaltonetworks.com/wp-content/uploads/2020/11/word-image-4.png)Figure 1. Geographical location of domains including HTML pages that were compromised by web skimmer malware from October 2019-October 2020.

The below Figure 2 shows the top eight countries the domain names belong to. While the United States has a majority share, it is notable that all of the top countries have a populace with a relatively high socioeconomic status. This seems sensible since most of the skimmer attacks target e-commerce websites, which attract users with spending power.

![Figure 2. Top eight countries, based on geographical location of domains compromised by web skimmer malware from October 2019-October 2020.](https://unit42.paloaltonetworks.com/wp-content/uploads/2020/11/word-image-5.png)Figure 2. Top eight countries, based on geographical location of domains compromised by web skimmer malware from October 2019-October 2020.

# How do they work? 

### Anatomy of a Web Skimmer

A web skimmer is a form of confidentiality attack that utilizes a piece of malicious code embedded in a legitimate website to secretly send personal information to an adversary. 


### Injection Method 

For a skimming attack to occur, code has to be injected into a target website. There are multiple methods that culprits use that all depend on how the target website is designed and what underlying software it uses. Some methods are as simple as a rogue employee from within the organization may insert skimmer code directly onto the target website's server, or an e-commerce platform may be attacked using a cross-site scripting (XSS) vulnerability. In what is referred to as a supply-chain attack, skimmers could be added to a website by taking advantage of a third-party resource. For instance, if a JavaScript library hosted on a content delivery network(CDN) was compromised by having a skimmer inserted into its code, any website that used the resource would be vulnerable to a skimming attack. 


### Attack Families

There are multiple forms of skimming script, some are inspired by others, but some are wholly original. Because of this, it is challenging to classify the various assault families into a clear taxonomy. RiskIQ, a California-based cyber security company, claims that there are at least seven different types of JavaScript skimming attacks, with an additional five variants not yet public. These attacks differ not only in their technical implementation but alsoin the sites they target. On the other side, Group-IB, a Russian cyber-defense company, claims to have discovered up to 38 distinct skimmer families.

The following table has main details of different groups of skimming attacks, as defined by RiskIQ. For more information and more in depth information on theses groups go to the following [link](https://www.imperial.ac.uk/media/imperial-college/faculty-of-engineering/computing/public/1819-ug-projects/BowerT-Industry-project-identifying-JavaScript-skimmers-on-high-value-websites.pdf).
![enter image description here](https://i.imgur.com/UVDaN6d.png)




### Obfuscation Techniques
![enter image description here](https://cybersecurity.asee.co/wp-content/uploads/2022/06/code-obfuscation-768x432.png)

Skimmers are built in client-side JavaScript, as opposed to other forms of malware that  operate server side, and as a result, anyone visiting a website that is infected can view its source code. Due to this, skimmer software is made to obfuscate their code as  much is possible. Otherwise, purposefully alter and modify the source code such that it keeps the desired behavior but is challenging for humans to read and understand what the code actually does.

Although, there are legitimate reasons for authors to obfuscate their code, such as attempts to hide the functionality of proprietary software or to hide email addresses from web crawlers.  Despite the fact that many malicious scripts are obfuscated by their authors, the presence of obfuscation does not automatically mean a script is malicious.

Attackers frequently use methods like string splitting to evade signature-based detection systems, which scan files for specific strings that could indicate the presence of malicious scripts. The string "Hello world," for instance, might be broken up into a number of smaller strings and then concatenated together, looking like **"Hel" + "lo w" + "orld."** Using escape sequences to type text in a different way is another typical method. To circumvent signature-based detection, the string **"x68x65x6cx6cx6f,"** which employs hexadecimal representations of ASCII letters, decodes to "Hello." As an example of a more sophisticated technique, tokenizing an entire file and replacing each token with smaller, equivalent base 62 values for compression and readability is demonstrated. To further confuse anyone attempting to understand the code, some scripts may even purposefully include dead code blocks (blocks of code that the program cannot access).


# How to avoid them ?
![enter image description here](https://images.squarespace-cdn.com/content/v1/51dc541ce4b03ebab8c5c88c/1572540465990-YHGMHCE8BYKE597RQNM8/cyber_safety.jpg?format=500w)

**Be informed**: it is always important to be informed when there might be breaches in any websites that internet users use.  This is not just limited to websites infected with web skimmers, but websites that might have had their data breached. 

Just in the year 2023, there have been numerous data breaches. For example, in January 2023, Norton Life Lock sent a notice to their customers in mid-January that over 6,000 of their customer accounts had been breached in recent weeks due to a “stuffing” attack. Stuffing attacks are when previously compromised passwords are used to hack into accounts that use a shared password. And just in March 2023 Chat GPT had a breach and had to release the following statement “In the hours before we took ChatGPT offline on Monday, it was possible for some users to see another active user’s first and last name, email address, payment address, the last four digits (only) of a credit card number, and credit card expiration date. Full credit card numbers were not exposed at any time.” 

**Be cautious**: For internet users, it is always recommended to track online activities for abnormal use and unauthorized payments from online banking services. If a person believes their credit card information was stolen as a result of a recent online purchase, they should contact their bank to freeze or replace their card immediately. Overall, a person should always know where their money is going.


## Sources
[Bower, Thomas. Imperial College London, *Identifying JavaScript Skimmers on High-Value Websites*.](https://www.imperial.ac.uk/media/imperial-college/faculty-of-engineering/computing/public/1819-ug-projects/BowerT-Industry-project-identifying-JavaScript-skimmers-on-high-value-websites.pdf)

Jin Chen, Tao Yan. “A Closer Look at the Web Skimmer.” *Unit 42,* 28 Jan. 2022, [unit42.paloaltonetworks.com/web-skimmer/](unit42.paloaltonetworks.com/web-skimmer/).
  
Farrelly, Jessica. “High-Profile Company Data Breaches 2023.” *Electric*, 23 May 2023, [www.electric.ai/blog/recent-big-company-data-breaches](www.electric.ai/blog/recent-big-company-data-breaches).

Opiah, Abigail. “Web Skimming Hackers Infiltrate over 40 Ecommerce Websites - That We Know Of.” *_TechRadar_*, 8 Dec. 2022, [www.techradar.com/news/web-skimming-hackers-infiltrate-over-40-ecommerce-websites-that-we-know-of](www.techradar.com/news/web-skimming-hackers-infiltrate-over-40-ecommerce-websites-that-we-know-of).
