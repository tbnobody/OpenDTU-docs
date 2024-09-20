# Getting Started

OpenDTU supports the ESP32 family of microcontrollers.

Depending on the inverter to be addressed, different RF modules are required.

- The HM series requires the NRF24L01+ module
- The HMS/HMT series requires the CMT2300A module

Please see the [inverter overview](inverter_overview.md) to see if your inverter is supported and to determine the required RF module.

For an easy start, use a "NodeMCU32 ESP32 DEVKIT DOIT" or "[ESP32 NodeMCU Development Board](esp32nodemcu_38pin.md)" with an ESP32-S3 or ESP-WROOM-32 chipset on it.

Sample Picture:

![NodeMCU-ESP32](../assets/images/nodemcu-esp32.png)

Boards with Ethernet-Connector and Power-over-Ethernet are also supported. For example [Olimex ESP32-POE](olimexpoeiso.md) or [LilyGo T-Internet-POE](https://www.lilygo.cc/products/t-internet-poe){target=_blank}

## Steps to build your own DTU

!!!note "Use of GPIOs"
    In general, ESP32 chips allow to use any function on any GPIO pin. There
    are a few restrictions, which are documented at the respective ESP32(-S3)
    DevKit subpages. Freely wire the logic pins between your ESP32(-S3) module
    and peripheral components. The important bit is to create and use a
    matching [device profile](../firmware/device_profiles.md).

1. Determine the [RF module](inverter_overview.md) you need
2. Get a ESP32 module.
3. Use a power suppy with 5 V and 1 A. The USB cable connected to your PC/Notebook may be powerful enough or may be not. Also the quality of the used USB cable might have an impact.
4. Wire the module and RF module
5. Wire a optional [display](display.md)
6. Wire optional [LEDs](led.md)
7. [Flash](../firmware/flash_esp.md) the firmware via USB
8. Create, upload, and select a matching [device profile](../firmware/device_profiles.md)
   which describes your hardware (or look at a profile first and connect the
   logic pins accordingly).
