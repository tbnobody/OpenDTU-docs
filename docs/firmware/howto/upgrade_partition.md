# Upgrade Partition

This guide applies only if the ESP was installed before 15.03.2023 and just upgraded using the OTA upgrade.

To be able to install further updates you have to update the partition table of the ESP32. Doing so will **erase** all configuration data. Over The Air update using the web interface is **NOT** possible!

!!! danger "Danger"

    Make sure you export a backup of your configuration files (`config.json` and `pin_mapping.json`) before continuing.

Follow the [flash instructions](../flash_esp.md) to completely reinstall the ESP. Make sure to install a binary called `opendtu-*.factory.bin`. It is of course also possible to use Visual Studio Code or the `platformio` command to install the latest version. The partition table is upgraded automatically.

After upgrading the ESP32 will open the integrated access point (AP) again. Just connect to it using the default password ("openDTU42"). If you are connected, just visit <http://192.168.4.1> and enter the "Configuration Management". Recover the previously backuped config files.
