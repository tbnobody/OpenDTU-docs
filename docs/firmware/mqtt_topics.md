# MQTT Topics

The base topic, as configured in the web GUI is prepended to all following topics.

## General topics

| Topic                                     | R / W | Description                                          | Value / Unit               |
| ----------------------------------------- | ----- | ---------------------------------------------------- | -------------------------- |
| `dtu/ip`                                  | R     | IP address of OpenDTU                                | IP address                 |
| `dtu/hostname`                            | R     | Current hostname of the dtu (as set in web GUI)      |                            |
| `dtu/rssi`                                | R     | WiFi network quality                                 | db value                   |
| `dtu/status`                              | R     | Indicates whether OpenDTU network is reachable       | online /  offline          |
| `dtu/temperature`                         | R     | Temperature of the ESP32                             | °C                         |
| `dtu/uptime`                              | R     | Time in seconds since startup                        | seconds                    |
| `dtu/heap/free`                           | R     | Available heap                                       | Bytes                      |
| `dtu/heap/size`                           | R     | Total heap size                                      | Bytes                      |
| `dtu/heap/minfree`                        | R     | Lowest level of free heap since boot                 | Bytes                      |
| `dtu/heap/maxalloc`                       | R     | Largest block of heap that can be allocated at once  | Bytes                      |

## Inverter total topics

Enabled inverter means, that only inverters with "Poll inverter data" enabled are considered.

| Topic                                     | R / W | Description                                          | Value / Unit               |
| ----------------------------------------- | ----- | ---------------------------------------------------- | -------------------------- |
| `ac/power`                                | R     | Sum of AC active power of all enabled inverters      | W                          |
| `ac/yieldtotal`                           | R     | Sum of energy converted to AC since reset watt hours of all enabled inverters | Kilo watt hours (kWh) |
| `ac/yieldday`                             | R     | Sum of energy converted to AC per day in watt hours of all enabled inverters | Watt hours (Wh)
| `ac/is_valid`                             | R     | Indicator whether all enabled inverters were reachable | 0 or 1                   |
| `dc/power`                                | R     | Sum of DC power of all enabled inverters             | Watt (W)                   |
| `dc/irradiation`                          | R     | Produced power of all enabled inverter stripes with defined irradiation settings divided by sum of all enabled inverters irradiation | % |
| `dc/is_valid`                             | R     | Indicator whether all enabled inverters were reachable | 0 or 1                   |

## Inverter specific topics

serial will be replaced with the serial number of the inverter.

| Topic                                     | R / W | Description                                          | Value / Unit               |
| ----------------------------------------- | ----- | ---------------------------------------------------- | -------------------------- |
| `[serial]/name`                           | R     | Name of the inverter as configured in web GUI        |                            |
| `[serial]/device/bootloaderversion`       | R     | Bootloader version of the inverter                   |                            |
| `[serial]/device/fwbuildversion`          | R     | Firmware version of the inverter                     |                            |
| `[serial]/device/fwbuilddatetime`         | R     | Build date / time of inverter firmware               |                            |
| `[serial]/device/hwpartnumber`            | R     | Hardware part number of the inverter                 |                            |
| `[serial]/device/hwversion`               | R     | Hardware version of the inverter                     |                            |
| `[serial]/radio/tx_request`               | R     | Amount of sent packet requests                       |                            |
| `[serial]/radio/tx_re_request`            | R     | Amount of sent fragment resend requests              |                            |
| `[serial]/radio/rx_success`               | R     | Amount of successfully received packets              |                            |
| `[serial]/radio/rx_fail_nothing`          | R     | Amount of failed packets, nothing was received       |                            |
| `[serial]/radio/rx_fail_partial`          | R     | Amount of failed packets, some fragments were missing |                            |
| `[serial]/radio/rx_fail_corrupt`          | R     | Amount of failed packets, payload corrupt            |                            |
| `[serial]/radio/rssi`                     | R     | RSSI of last received packet (Inverters with NRF24 module only support 2 states. > -64dBm and < -64dBm. In the first case -30 dBm is shown, in the second one -80 dBm) | dBm                        |
| `[serial]/status/reachable`               | R     | Indicates whether the inverter is reachable          | 0 or 1                     |
| `[serial]/status/producing`               | R     | Indicates whether the inverter is producing AC power | 0 or 1                     |
| `[serial]/status/last_update`             | R     | Unix timestamp of last inverter statistics update    | seconds since JAN 01 1970 (UTC) |

### AC channel / global specific topics

| Topic                                     | R / W | Description                                          | Value / Unit               |
| ----------------------------------------- | ----- | ---------------------------------------------------- | -------------------------- |
| `[serial]/0/current`                      | R     | AC current in ampere                                 | Ampere (A)                 |
| `[serial]/0/efficiency`                   | R     | Ratio AC Power over DC Power in percent              | %                          |
| `[serial]/0/frequency`                    | R     | AC frequency in hertz                                | Hertz (Hz)                 |
| `[serial]/0/power`                        | R     | AC active power in watts                             | Watt (W)                   |
| `[serial]/0/powerdc`                      | R     | DC power in watts                                    | Watt (W)                   |
| `[serial]/0/powerfactor`                  | R     | Power factor in percent                              | %                          |
| `[serial]/0/reactivepower`                | R     | AC reactive power in VAr                             | VAr                        |
| `[serial]/0/temperature`                  | R     | Temperature of inverter in degree celsius            | Degree Celsius (°C)        |
| `[serial]/0/voltage`                      | R     | AC voltage in volt                                   | Volt (V)                   |
| `[serial]/0/yieldday`                     | R     | Energy converted to AC per day in watt hours         | Watt hours (Wh)            |
| `[serial]/0/yieldtotal`                   | R     | Energy converted to AC since reset watt hours        | Kilo watt hours (kWh)      |

### DC input channel topics

[1-4] represents the different inputs. The amount depends on the inverter model.

| Topic                                     | R / W | Description                                          | Value / Unit               |
| ----------------------------------------- | ----- | ---------------------------------------------------- | -------------------------- |
| `[serial]/[1-4]/current`                  | R     | DC current of specific input in ampere               | Ampere (A)                 |
| `[serial]/[1-4]/name`                     | R     | Name of the DC input channel as configured in web GUI|                            |
| `[serial]/[1-4]/irradiation`              | R     | Ratio DC Power over set maximum power (in web GUI)   | %                          |
| `[serial]/[1-4]/power`                    | R     | DC power of specific input in watt                   | Watt (W)                   |
| `[serial]/[1-4]/voltage`                  | R     | DC voltage of specific input in volt                 | Volt (V)                   |
| `[serial]/[1-4]/yieldday`                 | R     | Energy converted to AC per day on specific input     | Watt hours (Wh)            |
| `[serial]/[1-4]/yieldtotal`               | R     | Energy converted to AC since reset on specific input | Kilo watt hours (kWh)      |

### Inverter limit specific topics

cmd topics are used to set values. Status topics are updated from values set in the inverter.

| Topic                                       | R / W | Description                                          | Value / Unit               |
| ------------------------------------------- | ----- | ---------------------------------------------------- | -------------------------- |
| `[serial]/status/limit_relative`            | R     | Current applied production limit of the inverter     | % of total possible output |
| `[serial]/status/limit_absolute`            | R     | Current applied production limit of the inverter     | Watt (W)                   |
| `[serial]/cmd/limit_persistent_relative`    | W     | Set the inverter limit as a percentage of total production capability. The  value will survive the night without power. The updated value will show up in the web GUI and limit_relative topic immediately. | %                          |
| `[serial]/cmd/limit_persistent_absolute`    | W     | Set the inverter limit as an absolute value. The value will survive the night without power. The updated value will set immediately within the inverter but show up in the web GUI and limit_absolute topic after around 4 minutes. If you are using an already known inverter (known Hardware ID), the updated value will show up within a few seconds. | Watt (W)                   |
| `[serial]/cmd/limit_nonpersistent_relative` | W     | Set the inverter limit as a percentage of total production capability. The  value will reset to the last persistent value at night without power. The updated value will show up in the web GUI and limit_relative topic immediately. The value must be published non-retained, otherwise it will be ignored! | %                          |
| `[serial]/cmd/limit_nonpersistent_absolute` | W     | Set the inverter limit as an absolute value. The value will reset to the last persistent value at night without power. The updated value will set immediately within the inverter but show up in the web GUI and limit_absolute topic after around 4 minutes. If you are using a already known inverter (known Hardware ID), the updated value will show up within a few seconds. The value must be published non-retained, otherwise it will be ignored! | Watt (W)                   |
| `[serial]/cmd/power`                        | W      | Turn the inverter on (1) or off (0)                 | 0 or 1                     |
| `[serial]/cmd/reset_rf_stats`               | W      | Reset the radio statistics                          | 1                          |
| `[serial]/cmd/restart`                      | W      | Restarts the inverters (also resets YieldDay)       | 1                          |
