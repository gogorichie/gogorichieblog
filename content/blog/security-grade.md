---
title: 'Taking My Security Grade From D to A'
description: ''
date: 2022-06-05T20:21:20-05:00
draft: false
categories: []
tags: ["Hugo","Blog", "Security"]
---

![Alt](https://gogorichiesitefiles.blob.core.windows.net/publicfiles/a-cert.jpg)

**Backstory**

For my website, security has always been a second-class citizen I've never treated it fairly outside of the basic practices of an SSL certificate and patching of the host and any plugins I might be using. I had the opportunity to join Scott Hanselman for a small group session hosted by my company and one of the things he talked about was providing server-side security and sound of mind to users. He asked the audience for someone's website address to show security vulnerabilities so I was quick to volunteer mine I assume my website was ok I knew that I was running a Hugo static hosted website on Netlify so I wasn’t truly concerned. He pulled up the website [securityheaders.com](http://www.securityheaders.com) and scanned gogorichie.com needless to say I was surprised my site ranked in as a D on a grading scale of A+ to R.

**What’s the tool looking at?**

I had never heard of [securityheaders.com](http://www.securityheaders.com) so this tool was new to me. It looking at the response header that the hosting server is providing to the client (user) as to what is missing or present and possibly missed configured. Not a full security review/assessment of the site but yet it’s another tool you can use to find issues and correct them on publicly accessible websites and applications. Since my site is a personal blog I have an easy opportunity to protect the readers of my site.

**What did I do to fix the errors?**

So the website runs on the Hugo static website engine adding a content security policy to the header file isn't that simple or so I thought. I did a quick Google search and landed on a website detailing how to add security headers to a Hugo site hosted by Netlify https://www.tobiasmcvey.com/adding-security-headers-in-hugo-with-netlify-and-report-uri/. Following the writer's instructions and During my research into solving the problem I came across some useful sites:
- Google has a great write up: https://developers.google.com/web/fundamentals/security/csp
- OWASP has a great list of Secure header syntax: https://owasp.org/www-project-secure-headers/
- Security headers quick reference list https://web.dev/security-headers/