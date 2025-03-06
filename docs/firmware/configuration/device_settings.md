# Device-Manager

## Screenshot

![Device-Manager](../../assets/images/screenshots/device_settings.png)

![Device-Manager Display](../../assets/images/screenshots/device_settings_display.png)

![Device-Manager LEDs](../../assets/images/screenshots/device_settings_led.png)

## Settings / Parameters

### Connection Settings

#### Selected profile :material-form-dropdown:{title="Dropdown"}

The drop-down shows an overview of all [Device Profiles](../device_profiles.md) available in your `pin_mapping.json` file. If you select one of the mappings and press **Save** the DTU will be restarted and the appropriate pins will be used.

#### Connection overview :material-table-lock:{title="Read only Table"}

The table shows all available pin configurations and how they are assigned currently (column "Active"). The column "Selected" shows the pin assignment according to the currently selected profile. If there are differences between "Active" and "Selected" the cells are highlighted. That means you can select different profiles (without clicking **Save**) and watch which pins will change.

### Display

These settings apply to a properly connected display. See [Device Profiles](../device_profiles.md) for display types and pin assignment.

#### Switch off if no solar :material-toggle-switch:{title="Switch"}

Turns off the display if no inverter is producing.

#### OLED Anti burn-in :material-toggle-switch:{title="Switch"}

Move the display a little bit on each update to prevent burn-in. This is useful especially for OLED displays.

#### Diagram mode :material-form-dropdown:{title="Dropdown"}

Allows to hide the diagram (`Off`), display it in parallel to the yield values (`Small`) or toggle between yield values and full screen diagram (`Fullscreen`)

#### Diagram duration :material-form-textbox:{title="Textbox"}

The time period which is shown in the Diagram. If you like e.g. show the production of the last hour, set the value to `3600`.

#### Display language :material-form-dropdown:{title="Dropdown"}

The language of the display text. (e.g. german "Heute" instead of english "Today")

#### Rotation :material-form-dropdown:{title="Dropdown"}

This allows to rotate the display content based on your alignment.

#### Contrast :material-tune-variant:{title="Slider"}

The contrast setting is only supported by some displays and the impact is also display specific.

### LEDs

These settings apply to properly connected LEDs[^1]. See [Device Profiles](../device_profiles.md) for LED function and pin assignment.

#### Equal brightness :material-toggle-switch:{title="Switch"}

When enabled, all sliders are set to the same value.

#### LED 0 brightness :material-tune-variant:{title="Slider"}

Sets the brightness of the LED to a specific value. This is useful if the LED is too dazzling, for example.

#### LED 1 brightness :material-tune-variant:{title="Slider"}

Please see [LED 0 brightness](#led-0-brightness).

[^1]: [Light-emitting diode](https://en.wikipedia.org/wiki/Light-emitting_diode){target=_blank}
