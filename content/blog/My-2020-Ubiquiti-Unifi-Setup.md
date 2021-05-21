---
title: 'My 2020 Ubiquiti Unifi Setup'
description: ''
date: 2021-05-20T23:05:31-05:00
draft: false
categories: [Home]
tags: []
---

I've been using Ubiquiti products since late 2018 to improve the wireless experience of my wife in our townhouse. I came across the product line while trying to solve the problem of getting decent wire coverage across a 2500 Sq foot two-story townhouse. I tried mesh network products from Netgear, Google, and some other companies always with the same problem repeaters would fail, the handoff between access points was awful, and most importantly the quality of service was crap leaving my wife frustrated. After tons of YouTube videos and articles, I decided to go with the Ubiquiti Unifi product line with the long-term plan of upgrading my whole home network over two years to spread out the cost. The products aren't cheap, they last long and they have a great resell value as far tech hardware goes.

**Iteration One**

My first Unifi network last 6 months it was simply a unifi 8 port switch, AC-Pro, and an AC-Lite. The controller running off a raspberry pi 3b. Pretty simple and just a tad bit under 200 bucks to get it up and running. The wife was happy, I was happy with the network performance, but the data nerd and DIYer within me itching for more now that I saw what software-defined networking could do.
![](https://img.community.ui.com/1248d56d-28f5-40f7-8033-b85fe16c42d7/stories/5595b8a8-66e8-40c5-92cc-0abb83a71cbc/4878ecda-9fc0-4422-bcca-cb33214f1b4a)

**Iteration Two**

Once I got my first taste of the UniFi controller interface and started to learn the power of it it became the only thing I wanted to use to manage my network. My next major update was the most expensive replacing my ISP-provided router with an Unifi Security Gateway. For my needs at the time I chose a USG 3P I felt like the USG-4 was a little more than my needs for the time. Around this time I replaced my home office switch with another 8 port switch. Followed a few months later by replacing my last non-Unifi hub with a 5 port USW Flex Mini in early 2020. I really love the mini it's one of my favorite UniFi products the location i put it in allowed for me to connect my SmartTV, Xbox One, Roku and HD Homerun and paint the full picture of all my network devices, where they are located at a really low cost.
![](https://img.community.ui.com/1248d56d-28f5-40f7-8033-b85fe16c42d7/stories/5595b8a8-66e8-40c5-92cc-0abb83a71cbc/ad77cb70-6d1b-4c4a-a5da-d9fdd57afc17)
![](https://img.community.ui.com/1248d56d-28f5-40f7-8033-b85fe16c42d7/stories/5595b8a8-66e8-40c5-92cc-0abb83a71cbc/6bd8c9a3-0761-4090-a54e-af36ecca5932)

**Iteration Three**

2020 brought many challenges and opportunities to invest and improve my home infrastructure. My wife's work transition to requiring her to begin to live stream and produce daily videos. As well as streaming every video in 4k. My job situation changed and I began to work from home as well like the rest of the world video conferencing became my daily thing as well. The savings of 4 hours a day in commuting time brought new energy to take on new home projects. Our house had cat5e ran to three rooms when we bought it so the first project was adding a cat 5e port to my wife's office and the two drops for the access points. Upon inspection of the wire quality, I noticed it was poor quality and had been spliced together again and again in multiple points in the cable. My quick project turned into a whole new network design and layout including 8 cat6 drops replacing all the cat5e. Replacing my two APs with the UniFi Lite 6 and the addition of an UniFi 8 port 150W switch to power everything. I also decided it was time to bring in a network rack, backup battery system, and a better firewall. I was eying a UDM Pro but a last-minute purchase of a USG-Pro-4. I found it on Offerup for 100 bucks so I couldn't pass it up. As said before the UniFi equipment has great resell value I've been able to fund 80% of this project through the selling of old equipment on eBay and Offerup.

My fiber connection enters house my in the garage so mounting the rack in the garage was ideal. Once the rack was in place I began the cable runs. Since I was replacing existing cable in the rooms and walls it was easy as securing the new cable to the old cable in the room and pulling it up and through the existing hole once I got it in the attic pulling the new cable to the new network rack. It took me about 3 hours to run and terminate the cables. I spent another 2 hours setting up and moving around equipment on my network rack before I felt like it was a good layout.
![](https://img.community.ui.com/1248d56d-28f5-40f7-8033-b85fe16c42d7/stories/5595b8a8-66e8-40c5-92cc-0abb83a71cbc/7fde596d-b7c9-4693-b700-3672d9c349cd)
![](https://img.community.ui.com/1248d56d-28f5-40f7-8033-b85fe16c42d7/stories/5595b8a8-66e8-40c5-92cc-0abb83a71cbc/99a5bc7b-b5dd-4269-b4d3-b8045d4e2f7f)

**Future Iterations**

I'm quite happy right now with the network design as of now, I'm getting great network performance throughout my home. But I'm already planning for the future upgrades to my rack replace the 8port POE switch and the 5 port USW Flex Mini with a 16 or 24 port POE switch. I could really use the ports as also plan on moving toward the Unifi Protect product line and replacing my Nest cameras and doorbell. It looks like there are some great updates on the horizon for the Protect product line. I might even replace my USG-Pro-4 with a UDM-Pro and move the non-POE devices to that device's built-in 8 port switch.
![](https://img.community.ui.com/1248d56d-28f5-40f7-8033-b85fe16c42d7/stories/5595b8a8-66e8-40c5-92cc-0abb83a71cbc/bf935478-0a35-4b90-a6a8-f9679ef424b2)