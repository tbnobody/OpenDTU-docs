# Firmware Update

## Over-The-Air

Once you have your OpenDTU running and connected to WLAN, you can do further updates through the web interface. Navigate to **Settings** --> **Firmware upgrade** and press the browse button. Select the firmware file from your local computer.

![Firmware Upgrade](../assets/images/screenshots/settings_firmwareupgrade.png)

If you've installed a pre-compiled firmware in the past (a firmware file which contained `opendtu-generic*.factory.bin` in it's filename) you can choose the appropriate binary without the suffix `.factory`.

You can find your currently installed binary file in **Info** --> **System** --> **PIO Environment**

If you have compiled the firmware by yourself, you'll find the firmware file (after a successful build process) under `.pio/build/generic/firmware.bin`.

After the successful upload, the OpenDTU immediately restarts into the new firmware.

!!! danger "Important hint"
    Make sure you reload the web interface after the update. Otherwise you will not see new settings and features. Normally it should be sufficient to reload the page with ++f5++ or by clicking on "Refresh". In some cases it may also be necessary to clear the browser cache. This can be done with the key combination ++ctrl+f5++, for example.

## Serial Update

### Using VSCode

If you've uploaded the firmware in the past using VSCode you can just follow the [compiling guide](compile_vscode.md) to upload it again. All settings are preserved.

### Using flash tool

If you are using a flash tool like `esptool.py`, the web-flasher or the espressif upload tool, make sure you flash the `.bin` file without the `.factory` suffix to address `0x10000`.
