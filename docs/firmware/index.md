# Firmware Installation

## Download Firmware

The pre-compiled binary files can be found on the GitHub [Releases
Page](https://github.com/tbnobody/OpenDTU/releases) (the right
column on the projects start page). Currently there are pre-compiled binaries
for ESP32 and ESP32-S3 MCUs.

## Factory-Binaries

!!! danger "Important"
    When flashing OpenDTU onto the ESP32 for the first time, you need
    to flash it with the **factory** firmware binary file.

Binaries with `.factory` in their name include the firmware, the respective
partition table, as well as the bootloader. Use these files to flash an ESP32
for the first time and after erasing the flash (to start from scratch).

## Overview of Firmware Variants

* All binary names start with `opendtu-` and include the respective
  PlatformIO (PIO) environment name.
* Use the non-factory binaries to perform [OTA updates](update.md).

| PIO Environment                        | MCU      | Flash Size          | Comment     |
| -------------------------------------- | -------- | ------------------- | ----------- |
| `generic_esp32[.factory].bin`          | ESP32    | 4&nbsp;MB           |  |
| `generic_esp32s3[.factory].bin`        | ESP32-S3 | &ge;&nbsp;8&nbsp;MB | For boards that only have a USB-UART bridge to the ESP32-S3. |
| `generic_esp32s3_usb[.factory].bin`    | ESP32-S3 | &ge;&nbsp;8&nbsp;MB | For boards with native USB connection. |
| `generic[.factory].bin`                | ESP32    | 4&nbsp;MB           | [Deprecated](howto/migrate_generic.md) |

!!! note "Note"
    All firmware variants require a [Device Profile](device_profiles.md) to be
    configured after installing the firmware.

## Write Firmware to ESP32

Follow the [instructions to write ESP32 flash memory](flash_esp.md).
