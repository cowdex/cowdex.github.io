---
title: My Learning Methodology for OWASP Top 10
date: 2022-10-12 12:00:00 +0100
categories: [Web Security, Web Application Vulnerabilities]
tags: [methodology , owasptop10, bugbounty, pentesting, webapplication]     # TAG names should always be lowercase
math: true
mermaid: true
---
Hello, to give something back to the infosec community I decided to start a new series on web application pen-testing. And this would be the first post.
<br>
As a Noob, I was struggling to find an effective way to learn about web application vulnerabilities, once you start looking for some learning resources and methodologies you’ll be lost in between Youtube videos, tweets, and even medium articles. I tried to put it all together and create my methodology. Here are my steps :

![Desktop View](/assets/img/web-roadmap.png){: width="972" height="589" }
_Web Vulnerabilities Roadmap_
<br>
## Step 1 : Learn the basics in a fun way
Picking up the initial idea about a web attack is an easy process if you have a guide walking you through it. when it comes to web vulnerabilities the best way to understand the basics is by watching a youtube video, [**PwnFunction**](https://youtube.com/playlist?list=PLI_rLWXMqpSl_TqX9bbisW-d7tDqcVvOJ) is my best channel as he explains using illustrations and some simple examples which makes it beginner friendly. [**Intigriti**](https://www.youtube.com/c/intigriti/featured) also has some good explanation videos.
<br>
> If you understand Arabic the best playlist for you would be : [**Web Application Penetration Testing Course**](https://youtube.com/playlist?list=PLv7cogHXoVhXvHPzIl1dWtBiYUAL8baHj) by Ebrahem Hegazy
<br>

## Step 2 : Dig a little bit deeper by reading a book chapter
After having a general idea about a web vulnerability, don't jump directly to solve labs or CTFs, try to understand its different scenarios, bypass & prevention techniques. There are a lot of books out there, the popular one is : **The Web Application Hacker's Handbook** but I don't use this book, it's about 912 pages and it's kinda outdated. Instead, I do recommend the [**Bug Bounty Bootcamp**](https://nostarch.com/bug-bounty-bootcamp) : it's a comprehensive guide for any web application hacker with a detailed exploration of the many vulnerabilities present in modern websites and the hands-on techniques you can use to most successfully exploit them.
The book contains a wide range of techniques :
- [x] Identify and successfully exploit a wide array of common web vulnerabilities
- [x] Set up a hacking environment, configure Burp Suite, and use its modules to intercept traffic and hunt for bugs
- [x] Chain together multiple bugs for maximum impact and higher payouts
- [x] Bypass protection mechanisms like input sanitization and blocklists to make your attacks succeed
- [x] Automate tedious bug-hunting tasks with fuzzing and bash scripting

![Desktop View](/assets/img/notion.png){: width="972" height="589" }
_My Notion Page for Portswigger Academy Notes_
<br>

## Step 3 : Get your hands dirty with labs
Now it's time to practice what you learned. When it comes to web security the best platform for you would be the [**Web Security Academy**](https://portswigger.net/web-security), it contains high-quality learning materials, interactive vulnerability labs, and video tutorials. You can learn at your own pace, wherever and whenever suits you. Best of all, **everything is free!**

The Web Security Academy is a living resource that we'll continue updating with new material and labs (**Now it has more than 220 lab**), covering the latest developments in web security research. We very much hope that the Web Security Academy will fulfill the purpose that The Web Application Hacker's Handbook has done in the past, and help the next generation of web hackers acquire the skills and knowledge that they need.

## Step 4 : Notetaking keeps you alert
Keeping notes is one of the key aspects of penetration testing, I personally use [**Notion**](https://notion.so) for several reasons :
 - [x] The Flexibility of a Paper Notebook
 - [x] Project and Task Management In One Place
 - [x] Digital Brain to Store, Organize, Share information
 - [x] Free for Personal Use
 - [x] Accessible on mobile devices

## Step 5 : Read writeups & Code, Play some CTFs
After completing all the previous steps you should take a look at some real-world scenarios, read POCs and writeups on [**Medium**](https://medium.com/@infosecwriteups) or [**hackerone**](https://hackerone.com/hacktivity) because when you read a writeup about a particular vulnerability or something else, you are reading it from someone else experience. 
<br>
You’ll sometimes come across the source code of an application you’re attacking. For example, you might be able to extract 
JavaScript code from a web application, find 
scripts stored on servers during the recon process or during a pentest you have access to source code  
If so, you are in luck! Reviewing code is one of the 
best ways to find vulnerabilities in applications. [**Souce Code Wiki**](https://securecode.wiki/) is a culmination of Secure Coding Practices for a wide range of languages. I read some PHP code there from time to time.
The last thing that I'm planning to start and I know that it's highly recommended is to start solving [**Pentesterlab**](https://pentesterlab.com/) as it contains some realistic scenarios and new CVEs...

Well, that was my simple methodology to learn web application vulnerabilities don't forget to share with your friends, happy hacking!