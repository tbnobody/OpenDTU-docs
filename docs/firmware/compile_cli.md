# Compile on the command line with PlatformIO Core

## Step by Step

1. Install [PlatformIO Core](https://platformio.org/install/cli){target=_blank} (PIO).
2. Clone the [source code repository](https://github.com/tbnobody/OpenDTU).
   You really have to clone the source code repository. Do not download and
   extract a source ZIP file. During the build process the Git hash is embedded
   into the firmware. If you merely download and extract the source ZIP file a
   build error will occur, as no Git status can be determined.
3. Adjust the serial port in file `platformio_override.ini` to your setup. The
   setting occurs twice:
    * `upload_port`
    * `monitor_port`
4. Build the firmware: `platformio run -e generic_esp32` (chose a suitable PIO environment)
5. Upload to ESP32 module: `platformio run -e generic_esp32 -t upload`

## Other Popular PlatformIO Tasks

    * Clean the sources:  `platformio run -e generic_esp32 -t clean`
    * Erase flash: `platformio run -e generic_esp32 -t erase`
