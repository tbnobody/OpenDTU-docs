# ESP32-S3 DevKit

These boards are generally a good choice to run OpenDTU if you aspire
to assemble your own hardware components. Have a look at the [user
guide](https://docs.espressif.com/projects/esp-idf/en/stable/esp32s3/hw-reference/esp32s3/user-guide-devkitc-1.html).

!!!warning
    Modules with 8 MB of PSRAM or 16 MB or more of flash memory use an octal
    SPI interface. Pins GPIO35, GPIO36 and GPIO37 are used for the internal
    communication between ESP32-S3 and SPI flash/PSRAM memory, thus not
    available for external use.

## Overview

The following is an overview of the original Espressif ESP32-S3 DevKit (USB-C
version). Many modules offered on well-known larger Chinese or local web stores
are usually merely compatible imitations.

![](../assets/images/hardware/espressif_esp32_s3_devkit_overview.jpg)

## Firmware

Use variant `generic_esp32s3_usb` on these boards. Three hardware UARTs will be
available. Console messages will appear on the USB connector which is wired to
the native USB stack of the ESP32-S3.
