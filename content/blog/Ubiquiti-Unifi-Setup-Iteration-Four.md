---
title: 'Ubiquiti Unifi Setup Iteration Four'
description: '2021 and early 2022 home network improvements'
date: 2022-06-26T17:05:31-05:00
draft: false
categories: []
tags: ["Home Network","Ubiquiti","Unifi"]
---



**Recap**

This is a continuation of my 2020 network overhaul. You can read the details about how this project started at this [link](/blog/my-2020-ubiquiti-unifi-setup/).  I ended the updates to my home network in 2020 in a good place and by that I mean everything was running smoothly with the full network being managed by software. There were no issues but lot’s of opportunities for improvement. So that left me thinking my 2021 improvements would be focused on reducing dependencies on 3rd party cloud services such as Ring and Google Nest cameras. Since everything was working just fine I was in no hurry to buy devices that were being sold with a markup. So I slowly began to acquire devices toward the end goal as devices went GA and deals popped up at Microcenter and eBay since this would be the most expensive part of the network.



**Iteration Four**


![December 2021 Network Topology](https://gogorichiesitefiles.blob.core.windows.net/publicfiles/2021-Network.JPG)

My most lengthy phase to date had three main goals. First, replace my Nest cameras and Ring doorbell with Unifi Protect cameras and doorbell. Second replace my USG-Pro-4 with a UDM-Pro that way I would gain extra ports for my non-POE devices as well as take advantage of the built-in controller, protect function, and IPS features. Third and final replace the 8-port switch and 5-port USW Flex Mini in my great room with a 16 or 24-port POE switch. I just need more ports in that area to accommodate all the devices of my family. The supply chain shortages and cost of the equipment caused this phase to take about 14 months. I spent about $1100 and recovered about $500 from the sale of my old USG, USG-Pro-4, Old AP and UniFi US-8 8 Port because with the Unifi device market so dried up old equipment still sell pretty high.


| Date | Device    | Source   |
| --- | --------- | ------- |
| Feb 01, 2021  | G3 Instant| Ui  |
| Jun 18, 2021  | G3 Flex| Ebay |
| Jun 29, 2021  | UDM-Pro| Ui   |
| Dec 09, 2021  | G3 Bullet| Ebay |
| Feb 08, 2022  | USW-Lite-16-PoE| Ui  |
| Mar 10, 2022  | G3 Instant| Ui  |
| Mar 10, 2022  | G4 Doorbell| Ui  |

![2021 Network Overview](https://gogorichiesitefiles.blob.core.windows.net/publicfiles/2021-NetworkOverview.JPG)


**Future Iteration**

The next iteration might be the beginning of the introduction of SFP+ modules and devices into my network. I'm starting to see some opportunities where might be able to push 10 Gbps and might ease some internal bandwidth restrictions for example I have an Unraid server and I would like to be able to read and write data as fast as possible from it. As well as swapping in more of the latest generation cameras and possibly smart flood lights around the exterior of my property.