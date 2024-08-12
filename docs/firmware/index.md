# Getting Started

## Download Firmware

The pre-compiled binary files can be found on the GitHub [Releases
Page](https://github.com/tbnobody/OpenDTU/releases) (the right
column on the projects start page). Currently there are pre-compiled binaries
for ESP32 and ESP32-S3 MCUs.

### Overview of pre-compiled binaries

| Binary                                  | MCU       | Device Profile mandatory | First Flash / OTA | Comment                                   |
| --------------------------------------- | --------- | ------------------------ | ----------------- | ----------------------------------------- |
| opendtu-generic.bin                     | ESP32     | No                       | OTA               | Deprecated!                               |
| opendtu-generic.factory.bin             | ESP32     | No                       | First Flash       | Deprecated!                               |
| opendtu-generic_esp32.bin               | ESP32     | Yes                      | OTA               | This will probably be your first update   |
| opendtu-generic_esp32.factory.bin       | ESP32     | Yes                      | First Flash       | This will probably be your first task     |
| opendtu-generic_esp32s3.bin             | ESP32-S3  | Yes                      | OTA               | For boards with usb-uart bridge           |
| opendtu-generic_esp32s3.factory.bin     | ESP32-S3  | Yes                      | First Flash       | For boards with usb-uart bridge           |
| opendtu-generic_esp32s3_usb.bin         | ESP32-S3  | Yes                      | OTA               | For boards with integrated usb connection |
| opendtu-generic_esp32s3_usb.factory.bin | ESP32-S3  | Yes                      | First Flash       | For boards with integrated usb connection |

!!! note "Note"
    All pre-compiled binaries require a mandatory [Device
    Profile](device_profiles.md). You have to upload one after flashing the
    firmware!

## Write Firmware to ESP32

!!! danger "Important"
    When flashing OpenDTU onto the ESP32 for the first time, you need to flash it over serial using the **factory** firmware binary file.
    You need to write the factory binary to the ESP32 flash chip at address `0x0`.

    The factory binary also contains a bootloader and partition scheme, which are needed to boot the ESP32.

Follow the [instructions to write ESP32 flash memory](flash_esp.md).
