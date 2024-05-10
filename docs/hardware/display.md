# Displays

OpenDTU currently supports different types of displays (see below). Currently only displays with a resolution of 128x64 pixel are supported. To activate a display you have to specify it's type and pin assignment either in a device profile. Please see [here](../firmware/device_profiles.md#implemented-configuration-values) for value `display.type` to determine the possible values. (On this page is also a link to several example configurations for different ESP boards)

## Display Settings

Display settings can also be found in the [Device Manager](../firmware/configuration/device_settings.md).

## Supported Models

### LCD Display PCD8544

* Size: 2,7"
* Resolution: 84x48 pixel
* Supported bus: SPI
* Type = 1

    ![SH1106](../assets/images/pcd8544-full.jpg){width=300}

### OLED Display SSD1306

* Size: 0,96"
* Resolution: 128x64 pixel
* Supported bus: I²C
* Type = 2

    ![SSD1306](../assets/images/ssd1306-full.jpg){width=300}

### OLED Display SH1106

* Size: 1,3"
* Resolution: 128x64 pixel
* Supported bus: I²C
* Type = 3

    ![SH1106](../assets/images/sh1106-full.png){width=300}

### OLED Display SSD1309

* Size: 2,42"
* Resolution: 128x64 pixel
* Supported bus: I²C
* Type = 4

    ![SSD1309](../assets/images/ssd1309-full.jpg){width=300}

### LCD Display ST7567S GM12864-59N

* Size: 2,1"
* Resolution: 128x64 pixel
* Supported bus: I²C
* Type = 5
* Datasheet: [link](../assets/datasheets/st7567s_gm12864-59n.webp){target=_blank}

    ![SSD1309](../assets/images/st7567s_gm12864-59n.png){width=300}

!!! note "Note"

    Due to the schematic of the display, it is not possible to turn off the backlight.
