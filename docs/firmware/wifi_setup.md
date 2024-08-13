# Wi-Fi Setup

At startup, when no Wi-Fi setup is found, the device will create an initial Access Point for configuring the device.

* After the initial flashing of the microcontroller, an Access Point called "OpenDTU-*" is opened. The default password is `openDTU42`.
* Use a web browser to open the address [http://192.168.4.1](http://192.168.4.1)
* Navigate to **Settings** --> **Network Settings** and enter your WiFi credentials. The username to access the config menu is "admin" and the password the same as for accessing the Access Point (default: `openDTU42`).
* OpenDTU then simultaneously connects to your WiFi AP with these credentials. Navigate to **Info** --> **Network** and look into section "Network Interface (Station)" for the IP address received via DHCP.
* If your WiFi AP uses an allow-list for MAC-addresses, please be aware that the ESP32 has two different MAC addresses for its AP and client modes, they are also listed at **Info** --> **Network**.
* When OpenDTU is connected to a configured WiFI AP, the "OpenDTU-*" Access Point is closed after 3 minutes.

!!! note "Note"
    * OpenDTU needs access to a working NTP server to get the current date & time. Both are sent to the inverter with each request. Default NTP server is `opendtu.pool.ntp.org`. If your network has different requirements please change accordingly (**Settings** --> **NTP Settings**).
    * Add your inverter in the inverter settings (**Settings** --> **Inverter Settings**)
