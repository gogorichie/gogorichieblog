---
title: "Office Meeting Indicator Version 2"
date: 2024-11-29T01:16:44-06:00
draft: false
tags: ["Home Assistant","Github"]
---

![ESP32 S3 Matrix 8x8 64 LED](https://gogorichiesitefiles.blob.core.windows.net/publicfiles/esp32-s3-matrix-5.jpg)

Previously, I made a YouTube video demonstrating how to automate the detection of whether a meeting is happening using Home Assistant and a light. In that video, I used an ESP32 board and LED light strips controlled by WLED, integrated with Home Assistant for the automation. Since then, I’ve discovered the [ESP32-S3 Matrix](https://amzn.to/3CPVFLV) a compact and versatile development board featuring an ESP32-S3 processor and an 8x8 RGB LED matrix with 64 integrated LEDs. This board is perfect for creating interactive lighting projects, digital art, and real-time visual displays. Its compact design makes it ideal for my setup: a small device placed inside a wine press located outside my office to signal my current meeting status with lights.

In this blog post, I’ll delve into the technical aspects of how I configured the ESP32-S3 Matrix (8x8 LED) to display a specific color based on the situation. For this project, I chose to use [FastLED](https://fastled.io/docs/), a powerful library designed for controlling addressable LEDs like those on the ESP32-S3 Matrix. FastLED offers precise control over individual pixels and supports complex lighting effects. While WLED is versatile, I opted to manage this device through [ESPHome](https://esphome.io/) and [Home Assistant](https://www.home-assistant.io/) for better integration into my setup.

Getting started with the ESP32-S3 Matrix is straightforward. You’ll need:

- An ESP32-S3 Matrix development board,
- ESPHome hosted on a computer, and
- A USB-C cable (note: the board does not include one).

To set it up:

1) Connect the device to your computer via USB-C.
1) Flash the firmware using ESPHome with the provided YAML configuration (available in the GitHub repository linked below).
1) Once the firmware is uploaded, the device should be ready to go.

The real power of this setup lies in the light configuration section of the YAML file, particularly around line 78. Using FastLED within ESPHome, you can unlock a variety of lighting effects and fine-tune the device's behavior to suit your needs.

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