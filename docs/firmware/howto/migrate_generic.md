# Migrate 'generic' to 'generic_esp32'

## Difference between `opendtu-generic.bin` and `opendtu-generic_esp32.bin`

The only difference between `opendtu-generic.bin` and `opendtu-generic_esp32.bin` is, that `opendtu-generic.bin` contains hard-coded pins for the nRF24 Module (and only for that module). The `opendtu-generic_esp32.bin` comes with no pre-configured pins and can be set-up by uploading a [device profile](../device_profiles.md).

## Migration process

* Make a backup of your configuration! (**Settings** --> **Config Management** --> **Backup** --> Select **config.json** --> Press **Backup**)
* Download the latest `opendtu-generic_esp32.bin` file from [here](https://github.com/tbnobody/OpenDTU/releases){target=_blank}
* Download [this](https://raw.githubusercontent.com/tbnobody/OpenDTU/master/docs/DeviceProfiles/nodemcu_esp32.json){target=_blank} device profile. It contains the same pin assignments as the hard-coded ones in `opendtu-generic.bin`.
* Upload the device profile. (**Settings** --> **Config Management** --> **Restore** --> Select **Pin Mapping (pin_mapping.json)** --> Select `nodemcu_esp32.json` --> Press **Restore**)
* The ESP reboots but does nothing different at the moment.
* Select the new uploaded device profile. This can already be done using the `opendtu-generic.bin` firmware. (**Settings** --> **Device-Manager** --> **Selected profile** --> Select `NRF24` --> Press **Save**)
* The ESP reboots and uses the pin assignment from the device profile. (Which makes no difference because they are equal to the old one)
* Upload the new firmware (**Settings** --> **Firmware Upgrade**)
* The ESP reboots
* All done!
