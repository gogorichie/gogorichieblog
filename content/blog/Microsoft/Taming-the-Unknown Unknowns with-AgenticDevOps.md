---
title: "Taming the Unknown Unknowns with Agentic DevOps"
date: "2026-01-05T08:00:00-06:00"
draft: false
tags: [“DevOps”, “AI”, “Agentic DevOps”, “GitHub Copilot”, “MCP”]
---

<div style="display:flex; justify-content:center;">
  <img src="https://gogorichiesitefiles.blob.core.windows.net/publicfiles/Classroom-rules-for-robot-students.png"
       alt="Teaching Agents The Rules"
       style="width:50%; height:auto;">
</div><br><br>


I remember this qoute from Donald Rumsfeld who was once the Secretary of defense and it goes ***“There are known knowns... there are known unknowns... but there are also unknown unknowns — the ones we don’t know we don’t know.”***

Rumsfeld definitely wasn’t talking about AI coding assistants when he said that, but the quote fits this moment in software development a little too well.

For years we’ve been pretty good at dealing with the known knowns in our systems: unit tests, linting, build pipelines, code reviews. We’ve also built processes to chip away at the known unknowns: load testing, chaos experiments, runbooks, and my favorite post-incident reviews.

But when you’re shipping complex apps, especially to the cloud, the scary stuff is still the unknown unknowns:
- The security hole hiding in an IaC template.
- The misconfigured policy that only shows up at 2 a.m.
- The weird edge case that nobody thought to test.

This is where I think agentic DevOps starts to matter.

**From “Copilot” to a Team of Specialists**

Most folks now are familiar with GitHub Copilot or similar tools: you type a bit of code or a comment, and the AI tries to help you complete it. That’s useful, but it’s still a very general-purpose assistant.

What I’m interested in is the next step: custom agents.

Think of them less like “one big AI helper” and more like a virtual team of specialists:
- An Application Security Agent that lives and breathes threat models, OWASP Top 10, and secure defaults.
- An Infrastructure-as-Code Agent that understands Terraform, Bicep, and your organization’s guardrails.
- A Cost Optimization Agent that has strong opinions about that new SKU you just added.
- A Reliability Agent that cares deeply about SLOs, retries, timeouts, and backoff strategies.

Instead of only relying on one “coding assistant,” you enhance it with custom agents designed around your actual domains and risks. That’s how you start shrinking the space of those unknown unknowns.

**What Are Custom Agents, Really?**

Under the hood, a custom agent is defined by a simple Markdown file, often called an agent profile.

That profile tells the agent:
- Who it is – its role, personality, and scope.
- What it cares about – security, IaC, observability, whatever you choose.
- What tools it can use – for example:
- Code search APIs
- Ticketing systems
- Security scanners
- Cloud management APIs
- Which MCP servers (Model Context Protocol) it can talk to – the bridge between the agent and your internal systems and data.

In other words, the profile is the job description and toolbox for that agent.

Instead of telling a generic AI, *“Help me with my code,” you’re now saying: “You are my Security Agent. You’re allowed to call this SAST tool, this secrets scanner, and this policy engine. Review this PR like it’s going into production at a bank.”* Now we’re not just generating code faster; we’re building smarter, context-aware checks around it.

**Human-in-the-Loop, On Purpose**

It’s really important to call this out: agentic DevOps is not “let the AI ship to production on its own.”

The whole process should be human-in-the-loop:
- Agents review and suggest.
- People approve, override, or ask for more context.
- Agents challenge assumptions instead of blindly agreeing.

Some examples:
- The security agent flags a risky pattern and explains why it’s a problem, linking to your organization’s internal security guidelines.
- The IaC agent asks: “You’re opening port 22 to the world. Is that intentional? Here are safer alternatives.”
- The reliability agent surfaces: “This dependency has no retry logic and calls an external API. Do you want me to suggest a pattern for that?”

The value isn’t just in catching issues; it’s in surfacing risks early, while it’s still cheap to fix them.

**Role Specialization: Agents Like Real Team Members**

Just like on a real DevOps team, you don’t ask one person to be the performance engineer, security architect, product owner, and DBA all at once (at least, you shouldn’t).

Custom agents work best when they’re specialized:
- Each agent has narrow, deep expertise.
- Each agent comes with specialized tools and instructions that match that expertise.
- You route tasks to the right agent, instead of asking a general-purpose assistant to “just figure it out.”

That specialization lets you encode your organizational knowledge directly into the agents:
- “In this company, all internet-facing services must go through this gateway.”
- “We always use this logging library in .NET apps.”
- “We never store secrets in plain text anywhere, and here are the scanners that enforce that.”

Over time, your agents become a living expression of “how we build and run software here.”

**Bringing It Back to the Unknown Unknowns**

So how does all this help with the Rumsfeld problem?

You still won’t catch everything. That’s just reality. But with agentic DevOps:
- You reduce the blast radius of the unknown unknowns by catching more issues in context.
- You shift left not just with pipelines and tests, but with intelligent, domain-aware checks.
- You codify your standards once and reuse them across teams via agents instead of hoping everyone reads the same wiki page.

GitHub Copilot (and others) are great at helping you move faster. Custom agents help you move safer. Here is a link to some of the custom [agents](https://github.com/Gogorichielab/.github/tree/main/agents) I've built and I'm currently using within my side projects. The combination of agents is where things get interesting.
<br>
<br>

This is still an emerging space, and I fully expect my definition of “Agentic DevOps” to evolve over time. But if you’re already using AI coding assistants today, the next natural question is *“How do I give this thing a real job on my team?”* That’s where custom, specialized, human-in-the-loop agents start to shine.
