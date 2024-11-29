---
title: "Office Meeting Indicator Version 2"
date: 2024-11-28T23:16:44-06:00
draft: false
tags: ["Home Assistant","Github"]
---

![ESP32 S3 Matrix 8x8 64 LED](https://gogorichiesitefiles.blob.core.windows.net/publicfiles/Designer.jfif)

Previously I made a YouTube video about how to automate identifying if there is a meeting going on or not using home assistant and a light. in the YouTube video I used and ESP32 board and some led light strips controlled by WLED configured in Home Assistant for the automation. I've since then discovered The [ESP32-S3 Matrix](https://amzn.to/3CPVFLV) a compact and versatile development board featuring an ESP32-S3 processor and an integrated with 64 LEDs in an 8x8 RGB LED matrix configuration, making it ideal for creating interactive lighting projects, digital art, and real-time visual displays. Making this the perfect small package  to go which is inside a wine press located outside my office to signal my current meeting status with lights.

In this blog post I'm going to go into the technical aspects of how I configured the ESP32 S3 Matrix 8x8 64 LED to be able to turn on and off with the selected color depending on the situation. For this project I chose to use [FastLED](https://fastled.io/docs/). It is a powerful library specifically designed for controlling addressable LEDs like the ones on the ESP32 S3 Matrix, offering fine-grained control over individual pixels and enabling complex lighting effects. While WLED is versatile for this project I wanted to be able to manage this device through [ESPHome](https://esphome.io/) and [Home Assistant](https://www.home-assistant.io/).

Setting Up the ESP32-S3 Matrix is pretty simple all you'll need is a ESP32-S3 Matrix Development Board, ESPHome Hosted on a computer, and a USB-C cable as the device doesn't include one. Once Connect to the device and flash the firmware with ESPHome using the code in the github repo below and you should be off and running. The real magic of using FastLED lies in the light section around line 78 of the YAML file.

{{< gist gogorichie 45c86c6faa31b1411e475bae184d88fa >}}

- **platform:** fastled_clockless: Specifies the FastLED library for controlling the LED matrix.
- **chipset: WS2812B:** Indicates the type of LED chips used in the matrix.
- **pin: GPIO14:** Defines the GPIO pin connected to the data pin of the LED matrix.
- **num_leds: 64:** Sets the total number of LEDs in the matrix.
- **rgb_order: RGB:** Specifies the order of the color channels (Red, Green, Blue).
- **name: "8x8 LED Matrix":** Assigns a name to the light entity.
- **id: led_matrix:** Provides a unique identifier for the light entity.
- **effects:** Defines a list of built-in effects that can be applied to the LED matrix.

Hope this blog post helps I would love some suggestions for improvements and I hope this helps others.

[https://github.com/gogorichie/esphome_esp32_s3_matrix](https://github.com/gogorichie/esphome_esp32_s3_matrix)