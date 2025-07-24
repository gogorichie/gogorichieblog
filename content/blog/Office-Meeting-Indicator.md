---
title: "How I Automated Meeting Presence for My Family"
description: "Using Home Assistant, ESPHome, and an ESP32-S3 Matrix to let my family know when I’m in a meeting"
date: 2025-07-06T08:00:00-05:00
draft: false
tags: ["Home Assistant", "Automation", "ESP32-S3", "ESPHome", "Work From Home"]
---
<div style="display: flex; justify-content: center; gap: 2rem;">
    <img src="https://gogorichiesitefiles.blob.core.windows.net/publicfiles/osf/ESP_Home_logo3.svg" alt="ESPHome logo" style="width: 200px;"/>
    <img src="https://gogorichiesitefiles.blob.core.windows.net/publicfiles/osf/home-assistant-wordmark-monochrome-on-light.png" alt="Home Assistant" style="width: 200px;"/>
</div>

<br/>

Like many folks post-2020, I’ve been working from home a lot more, and with that came a new set of challenges — one of them being how to let my family know when I’m in a meeting without yelling across the house or hanging a note on the door. I decided to solve that problem the way any tech nerd would — with a bit of home automation magic.

**The Idea**

The idea was simple: I wanted a visual indicator outside my home office that would show whether I was currently in a meeting or available. I had recently picked up an [ESP32-S3 with an 8x8 RGB LED matrix](https://amzn.to/4dEgk37) and figured this would be the perfect project to put it to use. Combine that with [Home Assistant](https://www.home-assistant.io/) running in Docker on my network and access to my Office 365 calendar, and I had the makings of a pretty slick solution.

**The Setup**

Let’s break down the components:

- **[Home Assistant](https://www.home-assistant.io/)** (Docker): I’ve got Home Assistant running in a Docker container on my local server. It’s the central nervous system of all my smart home automation.
- **[ICal Integration](https://github.com/tybritten/ical-sensor-homeassistant)**: Home Assistant reads my Office 365 work calendar using this community integration. It allows Home Assistant to pull upcoming events and determine if I'm currently in a meeting.
- **[Workday Integration](https://www.home-assistant.io/integrations/workday/)**: I didn’t want the display running on weekends or holidays, so I layered in the Workday integration to make sure the automation only runs on actual workdays.
- **ESPHome Integration**: I flashed the ESP32-S3 with [ESPHome](https://esphome.io/) and configured it to control the 8x8 LED matrix. ESPHome makes the display fully controllable via Home Assistant, letting me show different colors based on presence. You can check out my exact configuration on [GitHub here](https://github.com/gogorichie/esphome_esp32_s3_matrix).

**How It Works**

Each morning, Home Assistant checks if it’s a workday. If it is, it monitors my calendar throughout the day. When a meeting is in progress, the LED matrix lights up **red** — a clear visual signal for the rest of the house that I’m unavailable. When there are no meetings, it lights up **green** — giving everyone the all-clear.

It's compact, low-power, and super visible even from down the hallway. My family knows at a glance whether it’s okay to knock or not, and it’s been a surprisingly effective solution.

**Why I Love It**

There’s something satisfying about solving a real-world problem with a DIY solution. I could’ve bought some off-the-shelf indicator, but building it myself means I understand every part of how it works — and I can tweak it as my schedule or needs change.

If you’ve got a home office and want a low-effort, high-impact upgrade, I can’t recommend something like this enough. ESPHome with an ESP32-S3 Matrix is rock solid, [Home Assistant](https://www.home-assistant.io/) is incredibly flexible, and this tiny little display packs a big punch for making remote work just a bit smoother.

---

Let me know if you’d like me to walk through the Home Assistant automation side or expand the matrix display logic — happy to share.
