# NTP Settings

## Screenshot

![NTP Settings](../../assets/images/screenshots/ntp_settings.png)

## Settings / Parameters

### NTP Configuration

OpenDTU needs a proper synced clock to start fetching the inverter. (Every request contains the time. This synchronises the clock in the inverter at the same time. This is particularly important for the event display.)

#### Time Server :material-form-textbox:{title="Textbox"}

Hostname or IP address of your NTP[^1] server. The default value is ok unless your WiFi does not provide access to the internet. In this case you have to enter your own NTP server (mostly the IP of your router e.g. `192.168.178.1`).

#### Timezone :material-form-dropdown:{title="Dropdown"}

Select the city or timezone you are in. NTP[^1] deliver the current time as UTC[^2]. The timezone is used to calculate your specific current time.

#### Timezone Config :material-form-textbox-lock:{title="Read only Textbox"}

This information shows how the time zone is interpreted internally. It contains information regarding offsets to UTC[^2] and also regarding DST[^3].

### Location Configuration

The location coordinates are required to determine the sunset and sunrise. The sunset type adds an offset to that value. This is used e.g. to stop polling the inverter at night.

#### Latitude :material-form-textbox:{title="Textbox"}

Latitude of the location of your inverter in degree.

#### Longitude :material-form-textbox:{title="Textbox"}

Longitude of the location of your inverter in degree.

#### Sunset type :material-form-dropdown:{title="Dropdown"}

There are differnt "Sunset types" which add different offsets to the calculated time.
The following values are possible:

* Standard dawn (90.8°)
* Nautical dawn (102°)
* Civil dawn (96°)
* Astronomical dawn (102°)

For some locations there might be even no sunset / sunrise because the sun shines everytime or never. See [here](https://en.wikipedia.org/wiki/Twilight#Definitions_by_geometry){target=_blank} for further explanation.

### Manual Time Synchronization

#### Current OpenDTU Time :material-form-textbox-lock:{title="Read only Textbox"}

Shows the current time of the ESP MCU. This value is used for all further calculations.

#### Current Local Time :material-form-textbox-lock:{title="Read only Textbox"}

Shows the current time detected from your web browser.

#### Synchronize Time :material-button-cursor:{title="Button"}

Press this button to manually synchronize the ESP time with your local time. This can be usefull if no NTP server is available.

!!! note "Note"
    Keep in mind, that the time gets lost after a power cycle. Also note, that the time accuracy will be skewed badly, as it can not resynchronised regularly using a NTP server and the ESP32 microcontroller does not have a RTC[^4].

[^1]: [Network Time Protocol](https://en.wikipedia.org/wiki/Network_Time_Protocol){target=_blank}
[^2]: [Coordinated Universal Timeordic](https://en.wikipedia.org/wiki/Coordinated_Universal_Time){target=_blank}
[^3]: [Daylight saving time](https://en.wikipedia.org/wiki/Daylight_saving_time){target=_blank}
[^4]: [Real-time clock](https://en.wikipedia.org/wiki/Real-time_clock){target=_blank}
