---
title: "Using Home Assistant and AI to Build a Better 'I Need Help' Button"
date: "2026-08-07T04:02:00-05:00"
draft: true
---

At the end of spring, my wife had foot surgery. Like many people recovering from a lower-body injury, she spent a lot of time using a knee scooter to get around the house.

While I work from home most days, there is one small problem: I'm notoriously bad at checking my phone during the workday. Between meetings, coding, writing, and whatever project I'm currently focused on, a text message can sit unread for far longer than either of us would like.

Rather than relying on phone calls or text messages, I decided to build a simple "I Need Help" notification system using Home Assistant, local AI, and a button attached directly to her scooter.

## The Goal

The requirements were pretty straightforward:

- The button needed to stay with her at all times.
- One action should notify me that she needs assistance.
- The notification needed to be impossible to miss.
- A second action should allow her to cancel the request if she figured it out herself.
- Since I already run AI locally in my home lab, I wanted to make the notifications a little more interesting than a generic alert.

## The Hardware

The solution starts with a **Third Reality Smart Button, model 3RSB22BZ**, connected to Home Assistant through Zigbee2MQTT.

The button is mounted directly to my wife's knee scooter. Since the scooter goes wherever she goes, the button is always within reach. No need to carry a phone, yell across the house, or hope I happen to hear her from my office.

The Third Reality button supports multiple actions, which made it perfect for this project. I could use the same physical button for both requesting assistance and canceling that request.

For my setup:

- **Hold:** I need help.
- **Double press:** Never mind.

When Zigbee2MQTT detects one of those actions, Home Assistant receives the event and runs the appropriate automation.

Another benefit of using Zigbee is that the button doesn't depend on the Internet or a vendor's cloud service just to tell Home Assistant that it was pressed. Everything starts inside my home network, which is exactly what I wanted for something like this.

## Adding AI to the Mix

This is where things get a little more fun.

Instead of sending a static notification like:

> Wife needs help.

Home Assistant uses an AI Task to send a prompt to my local **Ollama** instance. I'm running **Gemma 3** locally in my home lab, so I can generate the notification without sending the prompt out to a cloud AI service.

The model generates a short message and returns it to Home Assistant. Home Assistant then uses that generated text for notifications across the house.

That includes my phone, smart devices around the house, and text-to-speech announcements on my HomePods.

So instead of hearing the same notification every time, I might get something like:

> Scooter command center has issued a help request.

Or:

> Recovery operations need immediate assistance.

The important part isn't really what Gemma 3 says. The important part is that when that button gets pressed, I'm going to know about it.

The AI just makes it more fun.

## Never Mind

Of course, sometimes you ask for help and then figure it out yourself.

That's where the double press comes in.

A double press triggers a second Home Assistant automation that tells Gemma 3 to generate a short, witty message letting me know she no longer needs assistance.

I might get something like:

> Situation resolved. No husband deployment required.

Or:

> False alarm. Continue whatever nerd project you're working on.

The cancellation gets distributed through the same notification system, so I know I don't need to stop what I'm doing and head across the house.

## Why AI?

The obvious question is: **why involve AI at all?**

The answer is pretty simple.

Because I can.

A static notification would work perfectly fine and would certainly be simpler. I could have Home Assistant announce "Assistance requested" every time she presses the button and call the project done.

But one of the reasons I enjoy running local AI models in my home lab is finding small, practical ways to actually use them.

This project gave me a way to combine **Home Assistant, Zigbee2MQTT, Ollama, Gemma 3, text-to-speech, and mobile notifications** to solve an actual problem around the house.

Gemma 3 isn't solving some complicated AI problem here. It's taking a very simple automation and making the interaction a little more human and a little less robotic.

And because the model is running on my Ollama instance, I'm doing it with AI infrastructure already sitting inside my home.

## The Best Automations Are Personal

A lot of home automation projects are about convenience.

Turn the lights on automatically.

Adjust the thermostat.

Tell me when somebody is at the front door.

Announce when a package gets delivered.

Those are all useful, and I've certainly built plenty of those automations.

But some of my favorite projects are the ones that solve a very specific problem for the people living in the house.

In this case, a Zigbee button attached to a knee scooter became a reliable way for my wife to get my attention while recovering from surgery.

Home Assistant handles the automation. Zigbee2MQTT handles the button. Ollama and Gemma 3 give the notifications a little personality. My phone and HomePods make sure I actually hear the request.

The technology behind it is fun, but that's not really the important part.

Sometimes the best smart home projects aren't about making the house smarter.

They're about making life a little easier for someone else.
