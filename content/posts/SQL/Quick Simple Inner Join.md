---
title: "Quick & Simple Inner Join"
date: 2011-12-19
draft: false
summary: ""
summaryImage: ""
tags: ["SQL"]
---

A business partner approached me the other day looking to share information with my company. Since parts numbers are recycled more often than lame jokes in my business one of the things we needed the business partner to provide was the brand of the part. The business partner said that this would be difficult to do since they were unfamiliar with linking data across tables in any manner. After understanding a little about the setup of the partner's tables I taught them to design a view linking the two primary tables where the data could be seen together through a view. Since their tables where normalized all they needed was an [INNER JOIN](http://en.wikipedia.org/wiki/Inner_join) statement to make this happen. Below is a sample of the statement i wrote for the partner.

_SELECT Inventory.[Prt#], Cross.Brand, Inventory.[OH-QTY], Inventory.Desc, Inventory.[Alloc-QTY], Inventory.[Pkg-QTY], Inventory.Cost, Inventory.Lstupdt  
_

_FROM [Cross] __INNER JOIN Inventory ON Cross.[Brand-ID] = Inventory.[Brand-ID]_

See what I mean by quick and simple inner join.