---
title: "Integrating My Shark IQ Navigator Vacuum Into Home Assistant"
date: "2026-08-07T04:02:00-05:00"
draft: true
---

For a long time I struggled to find a robot vacuum that both I liked from a technology perspective and my wife approved of from a day-to-day usability standpoint. That combination honestly matters more than most smart home people admit. You can have the coolest automation setup in the world, but if the device annoys your spouse, it’s not staying in the house long term.

After a lot of looking around, we ended up settling on a Shark IQ Navigator RV2110 vacuum. We actually picked it up on Amazon using referral gift cards, which made the purchase sting a little less. Once it arrived, I went through the standard setup process in the Shark app, connected it to my network, updated firmware, and got everything operational.

But getting the vacuum running normally was really just the beginning.

## Getting The Shark Into Home Assistant

The next thing I wanted was integration into my [Home Assistant](https://www.home-assistant.io/) environment. Naturally, I assumed I could just use the built-in Shark IQ integration, but of course my specific model wasn’t officially supported. That led me down the normal smart home rabbit hole of GitHub repositories, community projects, and figuring out what someone else had already reverse engineered.

Eventually I landed on [shark2mqtt](https://github.com/CamSoper/shark2mqtt). Since I already run MQTT throughout my house for multiple devices and automations, getting it connected was pretty painless. Mostly just configuration work providing credentials, broker information, and mapping the device correctly. While it still communicates outward through Shark’s cloud services for status updates, MQTT acts as the bridge bringing everything into Home Assistant.

Once integrated, the vacuum exposed itself cleanly into Home Assistant with:

- `vacuum.poppi_dos` as the primary vacuum entity
- Battery, charging, Wi-Fi, and error sensors
- Room-cleaning button entities
- A clean mode selector using `select.poppi_dos_clean_mode`

At that point the project started getting interesting.

The integration supports all the standard vacuum controls including start, pause, stop, and return-to-base actions. But what really sold me on the setup was the ability to trigger room-specific cleaning jobs independently. I now have dedicated room-cleaning entities for:

- Kitchen
- Family Room
- Den
- Foyer
- Office

That means I can tell the vacuum to clean only a specific room instead of wasting time running the entire house. It also supports Matrix/UltraClean deep cleaning modes along with advanced `vacuum.send_command` actions that can be leveraged for automations or multi-room cleaning routines.

## Building A Better Dashboard Card

Since the vacuum was now properly exposed inside Home Assistant, the next step was making the dashboard experience nicer. By default, Home Assistant provides a basic vacuum entity card which works fine, but I wanted something a little more polished and purpose-built.

That’s where the custom [vacuum-card](https://github.com/denysdovhan/vacuum-card) Lovelace card came into play.

The setup was honestly simple. Once I pointed the card at:

```yaml
entity: vacuum.poppi_dos
```

I immediately had a clean dashboard interface with controls and live status updates. From there I expanded things further by surfacing battery status, charging state, cleaning mode selection, and room-cleaning shortcuts directly into the dashboard. Room cleaning itself is handled through the generated `button.poppi_dos_clean_*` entities.

## Automating Room Cleaning With Home Assistant

One of the limitations of the Shark Robovac application is scheduling flexibility. Through the stock Shark app you can schedule the vacuum to clean the entire house, but you really can’t create room-specific schedules like “clean the kitchen every Tuesday night.”

That became one of the biggest reasons I wanted the vacuum integrated into Home Assistant instead of just relying on the manufacturer app.

Since the room-cleaning entities are exposed through MQTT into Home Assistant, I can automate specific rooms independently. In my case, I wanted the kitchen cleaned automatically overnight on selected days because that room gets dirty faster than the rest of the house.

To solve that problem, I created a Home Assistant automation that triggers the kitchen cleaning button entity automatically at 2:20 AM.

```yaml
alias: Kitchen Clean with Poppi
description: Automatically trigger the Poppi device to clean the kitchen on weekdays.
triggers:
  - trigger: time
    at: "02:20:00"
    weekday:
      - mon
      - tue
      - fri
      - thu
      - sat
conditions: []
actions:
  - action: button.press
    metadata: {}
    target:
      entity_id: button.poppi_dos_clean_kitchen
    data: {}
mode: single
```

This is where Home Assistant really starts separating itself from vendor ecosystems. Instead of being limited to whatever scheduling options Shark decided to expose in their mobile app, I can build automations around how we actually live in the house. For my needs this makes the Home Assistant integration much more powerful than simply using the standard Shark app.

One of my favorite things about Home Assistant is when devices stop feeling like standalone products and start becoming part of the larger ecosystem. The vacuum cleaner is now just another smart device in the house participating in automations, dashboards, and routines alongside lights, sensors, cameras, and everything else.

It’s funny how projects like this always start simple.

Buy a vacuum cleaner. Connect it to WiFi. Done.

Except if you’re into home automation, that’s never actually where it ends.
