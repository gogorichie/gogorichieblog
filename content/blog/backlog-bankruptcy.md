---
title: "It's Time to Declare Backlog Bankruptcy"
date: 2026-08-07T03:40:00-05:00
draft: true
tags: ["DevOps", "Agile", "Product Management", "Backlog"]
categories: ["DevOps"]
---

Over the last couple of weeks, I've spent some time reading about a topic that I think every software development team eventually encounters: **backlog bankruptcy**.

The idea is pretty simple. At some point a backlog can get so large, so old, and so disconnected from what the organization is actually trying to accomplish that continuing to maintain it provides less value than simply drawing a line and starting over.

That sounds extreme. Delete years of work? Hundreds or even thousands of carefully written user stories? Surely there is value in keeping all of that around.

But I've actually seen backlog bankruptcy work.

## I've Seen This Work

Years ago, I worked for an IT shop where our backlog had grown to more than **2,000 user stories**.

And we carried them.

Stories from months ago. Stories from years ago. Features someone once thought would be useful. Requests that had survived changes in priorities, teams, and leadership. Every time the development teams looked at the backlog, they weren't just looking at what we needed to build next. They were looking at years of features waiting for them.

Then a new CTO joined the organization and brought forward an idea that seemed pretty radical at the time: **draw a line and start over.**

Essentially, we declared backlog bankruptcy.

I'm not going to pretend everyone loved the idea. Feelings were hurt. People had spent time writing those stories, refining requirements, and advocating for features they believed were important. Archiving that work can feel like you're saying the work didn't matter.

But that wasn't really what we were saying.

We were acknowledging that the organization had changed, our priorities had changed, and carrying thousands of old stories wasn't helping us decide what mattered today.

So we drew the line.

What came afterward surprised me.

Instead of developers opening the backlog and seeing years of features waiting to be built, they saw work that actually represented where we were going. The backlog became manageable again. Conversations became focused on current problems instead of debating the priority of something someone requested three years earlier.

More importantly, **morale improved.**

There is something mentally exhausting about looking at a backlog you know your team could never realistically finish. You're starting every sprint knowing that no matter how much you accomplish, thousands of items are still waiting.

The clean start changed that.

We didn't suddenly have fewer business problems to solve. We didn't magically gain more developers. What changed was that the work in front of us felt achievable and relevant.

Looking back, that CTO wasn't throwing away our history. He was giving the development teams permission to stop carrying it.

## The Junk Drawer Problem

Recently I came across the article [It's Time to Declare Backlog Bankruptcy](https://betterways.substack.com/p/its-time-to-declare-backlog-bankruptcy), which compared the way teams treat backlogs to a junk drawer.

> "We abuse our Backlogs, treating them like junk drawers..."

Every house has one. Old batteries, random screws, mystery keys and things we're afraid to throw away because we might need them someday.

Software teams do exactly the same thing.

- Feature request from three years ago? Keep it.
- Bug nobody can reproduce? Keep it.
- Executive idea from two reorganizations ago? Keep it.
- Customer enhancement nobody has asked about since? Keep it.

Eventually the backlog becomes less of a planning tool and more of an archive.

The article makes another point that I think is important: stories written six months, a year, or five years ago may be more likely to cause harm than good.

Those stories were created based on assumptions that existed when they were written. The customer may have changed. The technology may have changed. The business certainly may have changed.

Yet the ticket remains.

## Just Declare Bankruptcy

This isn't a particularly new idea either. I found a [Hacker News discussion from 2016](https://news.ycombinator.com/item?id=10829735) where one commenter put it pretty simply:

> "Please just declare 'Backlog Bankruptcy'. Start a new project in JIRA or whatever."

There's another idea behind backlog bankruptcy that initially sounds scary: **if something is truly important, someone will ask for it again.**

That's probably true more often than we want to admit.

If a feature has been sitting untouched for three years and nobody has asked about it, is it really one of the organization's priorities?

Maybe the answer isn't to keep grooming it.

Maybe the answer is to let it go.

## The Tyranny of Existing Work

Christian Hartvig's article [The Tyranny of the Backlog](https://medium.com/@christian.hartvig/the-tyranny-of-the-backlog-how-product-teams-get-stuck-shipping-the-wrong-things-5e0f79886e01) takes this idea a step further.

Once something enters the backlog, it starts to gain legitimacy simply because it exists.

Instead of asking:

> "Should we still build this?"

We start asking:

- When will this get prioritized?
- Why hasn't this moved?
- Which sprint will this go into?
- Can we get an update on it?

The existence of the ticket creates an expectation that someday it will be completed.

That's where the backlog can start becoming a substitute for strategy.

A backlog should be the result of your strategy. Your strategy shouldn't be whatever happens to be sitting in your backlog.

## Software Fundamentals Haven't Changed

After reading about backlog bankruptcy, I also went back and looked at Microsoft's old [Software Development Fundamentals](https://learn.microsoft.com/en-us/shows/software-development-fundamentals/01) material.

The technology is old, but the fundamentals aren't.

Understand the problem. Gather requirements. Prioritize the work. Build the solution. Test it. Maintain it.

Notice what's missing?

**Maintain 4,000 Jira tickets forever.**

Over the years we've changed almost everything about how we build software. We've moved from TFS to Azure DevOps and GitHub. Git became the standard for version control. CI/CD became normal. Infrastructure became code. And now AI can help developers write code, tests and documentation.

Yet the basic reason we build software hasn't changed.

We're trying to solve a problem.

The backlog is simply one of the tools we use to decide which problem to solve next.

## AI Makes This Even More Important

I think backlog bankruptcy becomes even more interesting in the age of AI.

For years one of the reasons we held onto every feature request was that software was expensive to build. Something we couldn't afford to build today might become important enough to build next year.

AI is starting to change some of that equation.

Developers can scaffold applications, generate tests, create documentation and work through repetitive development tasks faster than before.

Implementation is getting cheaper.

**Deciding what we should build is becoming more important.**

If we can build things faster, carrying five years of feature requests doesn't necessarily become more valuable. It may just allow us to build the wrong things faster.

## What Should a Backlog Look Like?

I'm not suggesting every organization walk into work tomorrow morning and delete its entire backlog.

But I think every team should occasionally ask a very simple question:

> **How many of these items could we realistically complete in the next twelve months?**

If the answer is 100 and your backlog contains 2,500 items, then you probably don't have 2,500 priorities.

You have 100 priorities and 2,400 pieces of inventory.

I'd rather see something closer to this:

- **Next Sprint:** Highly refined and understood.
- **Next Quarter:** Prioritized and reasonably defined.
- **Next 6-12 Months:** Broad ideas and themes.
- **Older work:** Archive it unless there is a compelling reason to keep it active.

That doesn't mean the old work never happened. It doesn't mean the people who created it wasted their time.

It means today's team gets to make decisions based on today's problems.

## Final Thoughts

Having a large backlog doesn't mean you have a plan.

Sometimes it means you've avoided making decisions about what **not** to do.

The experience I had with more than 2,000 user stories changed the way I look at this. Drawing that line wasn't painless, but the clean start helped the development teams focus on work that was actually achievable. More importantly, they weren't coming into every sprint staring at years of features they knew they would probably never complete.

A backlog should help answer a simple question:

> **What is the most important thing we should work on next?**

If your backlog makes that question harder to answer instead of easier, maybe it's time to consider bankruptcy.

Because sometimes the best thing you can give a development team isn't another prioritized user story.

It's permission to stop carrying yesterday's priorities.
