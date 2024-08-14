# Compile on the command line with PlatformIO Core

* Install [PlatformIO Core](https://platformio.org/install/cli){target=_blank} (PIO).
* Clone the [code repository](https://github.com/tbnobody/OpenDTU).
  You really have to clone it, do not download and extract a source ZIP file.
  During the build process the GIT hash gets embedded into the firmware. If you
  download and extract the source ZIP file a build error will occur.
* Adjust the COM port in file `platformio_override.ini`. It occurs twice:
    * `upload_port`
    * `monitor_port`
* Build the firmware: `platformio run -e generic_esp32` (chose a suitable PIO environment)
* Upload to ESP32 module: `platformio run -e generic_esp32 -t upload`
* Other options:
    * Clean the sources:  `platformio run -e generic_esp32 -t clean`
    * Erase flash: `platformio run -e generic_esp32 -t erase`
