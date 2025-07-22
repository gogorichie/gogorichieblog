---
title: "Why I Left WordPress (And Never Looked Back)"
description: "After nearly two decades, I finally ditched WordPress for something leaner and more manageable"
date: 2025-07-22T18:00:00-05:00
draft: true
categories: []
tags: ["Hugo", "WordPress", "Static Sites", "Dev Blogging", "LLM", "Azure", "AppInsights"]
---

<img src="https://gogorichiesitefiles.blob.core.windows.net/publicfiles/trashing_wp.png" alt="WordPress" style="width:50%; display:block; margin:auto;" />

Back in college on July 9th, 2002, I registered *gogorichie.com* through GoDaddy. It was a spur-of-the-moment decision, driven by the curiosity of owning my own slice of the internet. Little did I know that domain would become my digital home for decades of blogging, experimentation, and tech journaling.

### A Love Letter to WordPress... With Conditions

From LiveJournal to Blogspot and eventually to a self-hosted WordPress install in 2011, my blog has lived many lives. WordPress gave me ultimate flexibility. I could mold my blog into anything I wanted thanks to its massive plugin ecosystem. Over the years, I posted nearly 3000 blog entries — trust me, a lot of it was garbage — but it was mine, and I loved that freedom.

That freedom came at a cost.

Running a WordPress site is no joke. Between plugin updates, theme conflicts, database backups, and the constant game of patching security holes — it felt more like managing a product than sharing my thoughts. Worse yet, I started dreading the upkeep more than I enjoyed writing. The final straw? Realizing I was spending more time fixing things than creating.

So in 2019, I pulled the plug.

### Going Static

At first, I replaced WordPress with a static HTML5 landing page hosted on GitHub — just a placeholder while I figured things out. But the more I reflected, the more I missed the early days of the web: when you uploaded a file and *that was it*. No admin panels, no plugins — just your words.

Then I discovered [Hugo](https://gohugo.io/). A fast, modern static site generator that lets me write in Markdown and deploy in seconds. It struck the perfect balance between flexibility and simplicity. My creativity came back to life.

Today, the site is deployed using [Azure Static Web Apps](https://learn.microsoft.com/en-us/azure/static-web-apps/getting-started) — simple GitHub integration, zero infrastructure hassle, and global CDN by default. It just works.

If you're curious about why I like Static Web Apps so much, check out my talk: [Azure Static Web Apps: The Cloud's New Electric Vehicle](https://www.gogorichie.com/blog/microsoft/azurespringcleaning2023/)

But what about media? Images, screenshots, and diagrams are all hosted separately in an **Azure Storage Account using Blob Storage**. I set it up with the default access tier as **Cool** since blog images are rarely hit after the initial publish. The cost? Basically free, thanks to Azure’s free tier and low usage.

So between Azure Static Web Apps for content and Azure Blob Storage for media, I’ve got a fully cloud-native blog architecture that’s fast, cheap, and effortless to maintain.

> 💡 You can check out the source code for this blog at [github.com/gogorichie/gogorichieblog](https://github.com/gogorichie/gogorichieblog)

### Observability with Application Insights

Another modern touch: I’ve wired up **Azure Application Insights** to monitor the site. Even with a static site, it’s useful to know how pages perform, where users drop off, and whether someone’s hammering your 404 page. With just a few lines of JavaScript, I get deep insights without compromising performance.

Plus, since I'm already using Application Insights in other Azure-based projects, it fits right into my existing dashboards. Lightweight, no server overhead, and incredibly informative.

### Why Hugo Works for Me

- No more databases to patch.
- No more plugin update roulette.
- Just Markdown, git, and build.

All of my posts are now written as Markdown files — literally just code. And that code lives in GitHub, versioned and trackable, like any software project. There’s something oddly satisfying about treating your writing the same way you’d treat code. It’s clean, transparent, and portable.

### Blog-as-Code Meets AI

As a bonus, this structure opens up some exciting possibilities. With all my historical blog content in structured Markdown, I’ve started exploring ways to feed it into my own large language model project — something I’m calling **GogorichieGPT**.

The idea? Build a personal knowledge assistant fine-tuned on my voice, my writing, and my experience. It’s still early days, but the foundation is already there: my blog is now data. And that data has the potential to fuel something bigger — something intelligent and uniquely me.

### The End of an Era, The Start of Something Better

Leaving WordPress felt like saying goodbye to an old friend — one who had become a bit too high-maintenance. But it also marked a return to what I originally loved about the web: simple publishing with minimal friction.

I’ve come full circle since that dorm room domain registration in 2002. Back then, I just wanted a place to share my thoughts. Today, I still do — but now, I don’t need a CMS empire to make that happen.

Thanks for the memories, WordPress It's time to move on to a less needy content system.
