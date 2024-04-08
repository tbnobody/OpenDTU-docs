# Home

![Logo](assets/images/logo.png){align=right}

## OpenDTU-OnBattery

!!! note "Upstream Project"

    OpenDTU-OnBattery is a fork of [OpenDTU][4] by Thomas Basler (tbnobody).

Open Source software to talk to [Hoymiles][1]{target=_blank} solar inverters
and battery peripherals. It is an alternative to Hoymiles Data Transfer Units
(DTUs), which sync data into the s-Miles cloud.

!!! note "Note"

    You can only use one DTU for a specific inverter. You cannot query an
    inverter with two DTUs. Mixing up multiple DTUs may lead to unexpected
    behavior!

## Key Features

* Dynamic Power Limiter to adjust one inverter's limit dynamically
* Power Meter interface to read the household power consumption
* Victron VE.Direct interface to communicate with Victron charge controllers
* Battery interface (JK BMS, Pylontech, Victron SmartShunt) to know a battery's state
* AC charger interface to control a Huawei AC charger

## Key Features inherited from the upstream project

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
* Prometheus API endpoint (/api/prometheus/metrics)
* English, German and French (partially translated) web interface
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

The upstream project was started from [a discussion on mikrocontroller.net](https://www.mikrocontroller.net/topic/525778){target=_blank}.
It's goal was to replace the original Hoymiles DTU (Telemetry Gateway), which uploads data to their cloud. With a lot of reverse engineering, the Hoymiles protocol was decrypted and analyzed.

## Support

For support using OpenDTU-OnBattery you can find us on Github or Discord:

[:material-github: Github Discussions][2]{target=_blank .md-button .md-button--primary }
[:fontawesome-brands-discord: Discord Chat][3]{target=_blank .md-button .md-button--primary }

[1]: https://www.hoymiles.com/
[2]: https://www.github.com/helgeerbe/OpenDTU-OnBattery/discussions
[3]: https://discord.gg/WzhxEY62mB
[4]: https://github.com/tbnobody/OpenDTU
