# Introduction

![Logo](assets/images/logo.png){align=right}

## OpenDTU

Open Source software to talk to [Hoymiles][1]{target=_blank} solar inverters. It is an alternative to their DTUs[^1] which sync everthing into the s-Miles cloud.

!!! note "Note"

    You can only use one DTU for a specific inverter. You cannot query a inverter with two DTUs. Mixing up multiple DTUs may lead to an unexpected behavior!

## Remarkable features

* Read live data from inverter
* Show inverters internal event log
* Show inverter information like firmware version, firmware build date, hardware revision and hardware version
* Show and set the current inverter limit
* Show the current grid profile settings
* Function to turn the inverter off and on
* Supports up to 10 inverters
* MQTT support (with TLS)
* Home Assistant MQTT Auto Discovery support
* Nice and fancy WebApp with visualization of current data
* Firmware upgrade using the web UI
* Time zone support
* Ethernet support
* [Prometheus API endpoint](3rd_party/prometheus_database.md) (/api/prometheus/metrics)
* English, german and french web interface
* Displays (SSD1306, SH1106, PCD8544)
* Status LEDs
* Configuration management (export / import configurations)
* Dark Theme

## Features for developers

* The microcontroller part
    * Build with Arduino PlatformIO Framework for the ESP32
    * Uses a fork of [ESPAsyncWebserver](https://github.com/yubox-node-org/ESPAsyncWebServer) and [espMqttClient](https://github.com/bertmelis/espMqttClient)

* The WebApp part
    * Build with [Vue.js](https://vuejs.org) and [Bootstrap](https://getbootstrap.com)
    * Source is written in TypeScript

## Background

This project was started from [this](https://www.mikrocontroller.net/topic/525778){target=_blank} discussion (Mikrocontroller.net).
It was the goal to replace the original Hoymiles DTU (Telemetry Gateway) with their cloud access. With a lot of reverse engineering the Hoymiles protocol was decrypted and analyzed.

## Support

For support using OpenDTU you can find us on Github or Discord:

[:material-github: Github Discussions][2]{target=_blank .md-button .md-button--primary }
[:fontawesome-brands-discord: Discord Chat][3]{target=_blank .md-button .md-button--primary }

## Donate

The firmware is opensource and free to use!

If you like this project you can show your appreciation by making a small donation.
This will help with offsetting the cost of the different hardware devices we support.

[![Buy a coffee](https://img.shields.io/badge/Kofi-donate-FF5E5B?style=for-the-badge&logo=kofi)](https://ko-fi.com/tbnobody){target=_blank}

[1]: https://www.hoymiles.com/
[2]: https://www.github.com/tbnobody/OpenDTU/discussions
[3]: https://discord.gg/WzhxEY62mB

[^1]: Data Transfer Unit
