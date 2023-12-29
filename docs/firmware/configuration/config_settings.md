# Config Management

## Screenshot

![Config Management](../../assets/images/screenshots/config_settings.png)

## Settings / Parameters

### Backup: Configuration File Backup

#### Backup the configuration file :material-form-dropdown:{title="Dropdown"}

Select the configuration file which you want to download.

#### Backup :material-button-cursor:{title="Button"}

Press this button to download the previously selected config file. The format of this file is `.json` and can be opened with any text editor.

### Restore: Restore the Configuration File

#### Target file selection :material-form-dropdown:{title="Dropdown"}

Select the file type which you are going to upload. The following values are possible:

* Main Config (config.json): A config file which was [previously backuped](#backup-configuration-file-backup)
* Pin Mapping (pin_mapping.json): A [Device Profile](../device_profiles.md) configuration file.

!!! warning "Warning"

    There is no further check if the uploaded file is valid. Properly check your settings!

#### Source file selection :material-file-upload:{title="File"}

Select the source file on your computer which you like to upload to the ESP.

#### Restore :material-button-cursor:{title="Button"}

Press this button to upload the selected source file to the specified target file. Afterwards the ESP automatically reboots and reads the uploaded file.

### Initialize: Perform Factory Reset

#### Restore Factory-Default Settings :material-button-cursor:{title="Button"}

This will delete the `config.json` file on the internal memory and therefor reset all settings to it's defaults. The `pin_mapping.json` file is preserved but the previously selected [Device Profile](../device_profiles.md) is set to default values.
After deleting all settings a automatic reboot is performed and the [initial Access Point](../wifi_setup.md) is opened again.
