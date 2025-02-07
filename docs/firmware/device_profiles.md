# Device Profiles

!!! note "Sample Profiles"
    Ready-to-use device profiles can be found [in the code
    repository](https://github.com/tbnobody/OpenDTU/tree/master/docs/DeviceProfiles){target=_blank}.

## Summary

Perform these steps to configure pin assignments for your board:

1. Upload an appropriate device profile (JSON file).
2. Afterwards, select a profile in the Web UI Device-Manager.

## Details

It is required to setup hardware settings like pin assignments or Ethernet
support using a JSON file. This tells OpenDTU what peripherals are
connected and how they are connected. The JSON file is uploaded using the
configuration management (**Settings** --> **Config Management**) in the web
interface. Select "Pin Mapping (pin_mapping.json)" in the dropdown menu of the
"Restore" section and choose the file to upload, then click the "Restore" button.

After the file was uploaded, the ESP performs a reboot. This is required as the
pin settings could have changed within the file and pin assignments are
initialized when booting.

To initially select or to change a device profile, navigate to **Settings** -->
**Device-Manager** and select the appropriate profile. When changing the device
profile, the ESP reboots. You can see the current (Active) and the new
(Selected) pin assignment in the table below the combobox.

The JSON file can contain multiple profiles. Each profile requires a name and
the respective parameters. If any parameter is not set, the default value `-1`
("not in use") will be effective.

## Structure of the JSON file

!!!note "Examples"
    These profiles are partially incomplete and merely serve as example snippets.

```json
[
    {
        "name": "Generic NodeMCU 38 pin with SSD1306 display",
        "nrf24": {
            "miso": 19,
            "mosi": 23,
            "clk": 18,
            "irq": 16,
            "en": 4,
            "cs": 5
        },
        "display": {
            "type": 2,
            "data": 21,
            "clk": 22
        },
        "eth": {
            "enabled": false,
            "phy_addr": -1,
            "power": -1,
            "mdc": -1,
            "mdio": -1,
            "type": -1,
            "clk_mode": -1
        }
    },
    {
        "name": "Generic NodeMCU 38 pin with SSD1306",
        "nrf24": {
            "miso": 19,
            "mosi": 23,
            "clk": 18,
            "irq": 16,
            "en": 4,
            "cs": 5
        },
        "eth": {
            "enabled": false,
            "phy_addr": -1,
            "power": -1,
            "mdc": -1,
            "mdio": -1,
            "type": -1,
            "clk_mode": -1
        },
        "display": {
            "type": 2,
            "data": 21,
            "clk": 22
        }
    },
    {
        "name": "Olimex ESP32-POE",
        "links": [
            {"name": "Datasheet", "url": "https://www.olimex.com/Products/IoT/ESP32/ESP32-POE/open-source-hardware"}
        ],
        "nrf24": {
            "miso": 15,
            "mosi": 2,
            "clk": 14,
            "irq": 13,
            "en": 16,
            "cs": 5
        },
        "eth": {
            "enabled": true,
            "phy_addr": 0,
            "power": 12,
            "mdc": 23,
            "mdio": 18,
            "type": 0,
            "clk_mode": 3
        }
    }
]
```

!!! note "Note"
    Please be aware that numerical values used in the profile `.json` file are
    **ESP chip GPIO numbers** (NOT physical Pin numbers).

## Implemented configuration values

| Parameter     | Data Type | Description |
| ------------- | --------- | ----------- |
| name          | string    | Unique name of the profile (max 63 characters) |
| links         | array     | Must contain a object with the properties **name** and **url**. For each object a button is shown in the Device-Manager
| nrf24.miso    | number    | MISO Pin |
| nrf24.mosi    | number    | MOSI Pin |
| nrf24.clk     | number    | Clock Pin |
| nrf24.irq     | number    | Interrupt Pin |
| nrf24.en      | number    | Enable Pin |
| nrf24.cs      | number    | Chip Select Pin |
| cmt.sdio      | number    | SDIO Pin |
| cmt.clk       | number    | CLK Pin |
| cmt.cs        | number    | CS Pin |
| cmt.fcs       | number    | FCS Pin |
| cmt.gpio2     | number    | GPIO2 Pin (optional) |
| cmt.gpio3     | number    | GPIO3 Pin (optional) |
| eth.enabled   | boolean   | Enable/Disable the ethernet stack |
| eth.phy_addr  | number    | Unique PHY addr |
| eth.power     | number    | Power Pin (if available). Use -1 for not assigned pins. |
| eth.mdc       | number    | Serial Management Interface MDC Pin. Use -1 for not assigned pins. |
| eth.mdio      | number    | Serial Management Interface MDIO Pin. Use -1 for not assigned pins. |
| eth.type      | number    | Possible values:<ul><li>0 = ETH_PHY_LAN8720</li><li>1 = ETH_PHY_TLK110</li><li>2 = ETH_PHY_RTL8201</li><li>3 = ETH_PHY_DP83848</li><li>4 = ETH_PHY_DM9051</li><li>5 = ETH_PHY_KSZ8041</li><li>6 = ETH_PHY_KSZ8081</li></ul> |
| eth.clk_mode  | number    | Possible values:<ul><li>0 = ETH_CLOCK_GPIO0_IN</li><li>1 = ETH_CLOCK_GPIO0_OUT</li><li>2 = ETH_CLOCK_GPIO16_OUT</li><li>3 = ETH_CLOCK_GPIO17_OUT</li></ul> |
| w5500.mosi    | number    | Use -1 for not assigned pins. |
| w5500.miso    | number    | Use -1 for not assigned pins. |
| w5500.sclk    | number    | Use -1 for not assigned pins. |
| w5500.cs      | number    | Use -1 for not assigned pins. |
| w5500.int     | number    | Use -1 for not assigned pins. |
| w5500.rst     | number    | Use -1 for not assigned pins. |
| display.type  | number    | Specify type of display. Possible values:<ul><li>0 = None (default)</li><li>1 = PCD8544</li><li>2 = SSD1306</li><li>3 = SH1106</li><li>4 = SSD1309</li><li>5 = ST7567S GM12864-59N</li></ul> |
| display.data  | number    | Data Pin (e.g. SDA for i2c displays) required for all displays. Use -1 for not assigned pins. |
| display.clk   | number    | Clock Pin (e.g. SCL for i2c displays) required for SSD1306 and SH1106. Use -1 for not assigned pins. |
| display.cs    | number    | Chip Select Pin required for PCD8544. Use -1 for not assigned pins. |
| display.reset | number    | Reset Pin required for PCD8544, optional for all other displays. Use -1 for not assigned pins. |
| led.led0      | number    | LED pin for network indication. <ul><li>Blinking = WLAN connected but NTP & MQTT (if enabled) disconnected.</li><li>On = WLAN, NTP, MQTT connected.</li><li>Off = Network not connected</li></ul> |
| led.led1      | number    | LED pin for inverter indication. <ul><li>On = All inverters reachable & producing.</li><li>Blinking = All inverters reachable but not producing.</li><li>Off = At least one inverter is not reachable.</li></ul> Only inverters with polling enabled are considered. |
