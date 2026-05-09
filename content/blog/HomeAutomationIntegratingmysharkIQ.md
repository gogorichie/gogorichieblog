---
title: "Integrating My Shark IQ Navigator Vacuum Into Home Assistant"
date: 2026-05-08
draft: false
tags: ["Home Assistant"]
categories: ["Home Automation"]
---

# Integrating My Shark IQ Navigator Vacuum Into Home Assistant

For a long time I struggled to find a robot vacuum that both I liked from a technology perspective and my wife approved of from a day-to-day usability standpoint. That combination honestly matters more than most smart home people admit. You can have the coolest automation setup in the world, but if the device annoys your spouse, it’s not staying in the house long term.

After a lot of looking around, we ended up settling on a Shark IQ Navigator vacuum. We actually picked it up on Amazon using referral gift cards, which made the purchase sting a little less. Once it arrived, I went through the standard setup process in the Shark app, connected it to my network, updated firmware, and got everything operational.

But getting the vacuum running normally was really just the beginning.

The next thing I wanted was integration into my [Home Assistant](https://www.home-assistant.io/) environment. Naturally, I assumed I could just use the built-in Shark IQ integration, but of course my specific model wasn’t officially supported. That led me down the normal smart home rabbit hole of GitHub repositories, community projects, and figuring out what someone else had already reverse engineered.

Eventually I landed on [shark2mqtt](https://github.com/CamSoper/shark2mqtt). Since I already run MQTT throughout my house for multiple devices and automations, getting it connected was pretty painless. Mostly just configuration work providing credentials, broker information, and mapping the device correctly. While it still communicates outward through Shark’s cloud services for status updates, MQTT acts as the bridge bringing everything locally into Home Assistant.

Once integrated, the vacuum exposed itself cleanly into Home Assistant with:

- `vacuum.poppi_dos` as the primary vacuum entity
- Battery, charging, Wi-Fi, and error sensors
- Room-cleaning button entities
- A clean mode selector entity for switching cleaning behavior

At that point the project started getting interesting.

The integration supports all the standard vacuum controls including start, pause, stop, and return-to-base actions. But what really sold me on the setup was the ability to trigger room-specific cleaning jobs independently. I now have dedicated room entities for:

- Kitchen
- Family Room
- Den
- Foyer
- Office

That means I can tell the vacuum to clean only a specific room instead of wasting time running the entire house. It also supports Matrix and UltraClean deep cleaning modes along with advanced `vacuum.send_command` actions that can be leveraged for automations or multi-room cleaning routines.

Since the vacuum was now properly exposed inside Home Assistant, the next step was making the dashboard experience nicer. By default, Home Assistant provides a basic vacuum entity card which works fine, but I wanted something a little more polished and purpose-built.

That’s where the custom [vacuum-card](https://github.com/denysdovhan/vacuum-card) Lovelace card came into play.

The setup was honestly simple. Once I pointed the card at:

```yaml
entity: vacuum.poppi_dos
```

I immediately had a clean dashboard interface with controls and live status updates. From there I expanded things further by surfacing battery status, charging state, cleaning mode selection, and room-cleaning shortcuts directly into the dashboard.

One of my favorite things about Home Assistant is when devices stop feeling like standalone products and start becoming part of the larger ecosystem. The vacuum cleaner is now just another smart device in the house participating in automations, dashboards, and routines alongside lights, sensors, cameras, and everything else.

It’s funny how projects like this always start simple.

Buy a vacuum cleaner. Connect it to WiFi. Done.

Except if you’re into home automation, that’s never actually where it ends.
````
