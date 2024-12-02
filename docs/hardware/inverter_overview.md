# Inverter Overview

!!! note "TSUN compatibility remark"
    Compatibility with OpenDTU is most likely related to the serial number of the inverter. Current findings indicate that TSUN inverters with a serial number starting with "11" are supported, whereby inverters with a serial number starting with "10" are not.

!!! note "Hoymiles HMS-xxxx-xT-NA compatibility remark"
    You have to change the Country/Region in the [DTU settings](../firmware/configuration/dtu_settings.md#cmt2300a-regioncountry).

!!! note "Inverters with integrated WiFi are not supported"
    All inverters with integrated WiFi which can be identified by the "W" in the name (e.g. HMS-xxxW) are not supported by OpenDTU.

| Model                | Required RF Module | DC Inputs | MPP-Tracker | AC Phases | Serial Prefix          |
| ---------------------| ------------------ | :-------: | :---------: | :-------: | :--------------------: |
| Hoymiles HM-300-1T   | NRF24L01+          | 1         | 1           | 1         | `1121`                 |
| Hoymiles HM-350-1T   | NRF24L01+          | 1         | 1           | 1         | `1121`                 |
| Hoymiles HM-400-1T   | NRF24L01+          | 1         | 1           | 1         | `1121`                 |
| Hoymiles HM-600-2T   | NRF24L01+          | 2         | 2           | 1         | `1141`                 |
| Hoymiles HM-700-2T   | NRF24L01+          | 2         | 2           | 1         | `1141`                 |
| Hoymiles HM-800-2T   | NRF24L01+          | 2         | 2           | 1         | `1141`                 |
| Hoymiles HM-1000-4T  | NRF24L01+          | 4         | 2           | 1         | `1161`                 |
| Hoymiles HM-1200-4T  | NRF24L01+          | 4         | 2           | 1         | `1161`                 |
| Hoymiles HM-1500-4T  | NRF24L01+          | 4         | 2           | 1         | `1161`                 |
| Hoymiles HMS-300-1T  | CMT2300A           | 1         | 1           | 1         | `1124`                 |
| Hoymiles HMS-350-1T  | CMT2300A           | 1         | 1           | 1         | `1124`                 |
| Hoymiles HMS-400-1T  | CMT2300A           | 1         | 1           | 1         | `1124`                 |
| Hoymiles HMS-400BM   | CMT2300A           | 1         | 1           | 1         | `1124`                 |
| Hoymiles HMS-450-1T  | CMT2300A           | 1         | 1           | 1         | `1124`, `1400`         |
| Hoymiles HMS-500-1T  | CMT2300A           | 1         | 1           | 1         | `1124`, `1125`         |
| Hoymiles HMS-600-2T  | CMT2300A           | 2         | 2           | 1         | `1143`, `1144`, `1410` |
| Hoymiles HMS-700-2T  | CMT2300A           | 2         | 2           | 1         | `1143`, `1144`, `1410` |
| Hoymiles HMS-800-2T  | CMT2300A           | 2         | 2           | 1         | `1143`, `1144`, `1410` |
| Hoymiles HMS-900-2T  | CMT2300A           | 2         | 2           | 1         | `1143`, `1144`, `1410` |
| Hoymiles HMS-1000-2T | CMT2300A           | 2         | 2           | 1         | `1143`, `1144`, `1410` |
| Hoymiles HMS-1600-4T | CMT2300A           | 4         | 4           | 1         | `1164`                 |
| Hoymiles HMS-1800-4T | CMT2300A           | 4         | 4           | 1         | `1164`                 |
| Hoymiles HMS-2000-4T | CMT2300A           | 4         | 4           | 1         | `1164`                 |
| Hoymiles HMT-1600-4T | CMT2300A           | 4         | 2           | 3         | `1361`                 |
| Hoymiles HMT-1800-4T | CMT2300A           | 4         | 2           | 3         | `1361`                 |
| Hoymiles HMT-2000-4T | CMT2300A           | 4         | 2           | 3         | `1361`                 |
| Hoymiles HMT-1800-6T | CMT2300A           | 6         | 3           | 3         | `1382`                 |
| Hoymiles HMT-2250-6T | CMT2300A           | 6         | 3           | 3         | `1382`                 |
| Solenso SOL-H350     | NRF24L01+          | 1         | 1           | 1         | `1121`                 |
| Solenso SOL-H400     | NRF24L01+          | 1         | 1           | 1         | `1121`                 |
| Solenso SOL-H800     | NRF24L01+          | 2         | 2           | 1         | `1141`                 |
| TSUN TSOL-M350       | NRF24L01+          | 1         | 1           | 1         | `1121`                 |
| TSUN TSOL-M800       | NRF24L01+          | 2         | 2           | 1         | `1141`                 |
| TSUN TSOL-M1600      | NRF24L01+          | 4         | 2           | 1         | `1161`                 |
| E-Star HERF-300      | NRF24L01+          | 1         | 1           | 1         | `A210`->`2841`         |
| E-Star HERF-800      | NRF24L01+          | 2         | 2           | 1         | `A110`->`2821`         |
| E-Star HERF-1600     | NRF24L01+          | 4         | 2           | 1         | `A010`->`2801`         |
| E-Star HERF-1800     | NRF24L01+          | 4         | 2           | 1         | `A010`->`2801`         |
