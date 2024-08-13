# Wi-Fi Setup

After startup, the device will act as an Access Point (AP) to allow (initial) configuration[^1].

* After the initial flashing of the microcontroller, an Access Point called
  "OpenDTU-*" is opened. The default password is `openDTU42`.
* Use a web browser to visit [http://192.168.4.1](http://192.168.4.1).
* The username to access config menus is "admin" and the password is the same
  as for accessing the Access Point (default: `openDTU42`).
* Navigate to **Settings** --> **Network Settings** and enter your Wi-Fi
  credentials.
* OpenDTU then simultaneously connects to your Wi-Fi AP with these
  credentials. Navigate to **Info** --> **Network** and look into section
  "Network Interface (Station)" for the IP address received via DHCP.
* If your Wi-Fi AP uses an allow-list for MAC-addresses, please be aware that
  the ESP32 has two different MAC addresses for its AP and client modes. These
  MAC addresses are also listed at **Info** --> **Network**.
* When OpenDTU is connected to a configured Wi-Fi AP as a client, the
  "OpenDTU-*" Access Point is closed after 3 minutes (timeout is configurable).

!!! note "Note"
    * OpenDTU needs access to a working NTP server to get the current
      date & time. Both are sent to the inverter with each request. Default NTP
      server is `opendtu.pool.ntp.org`. If your network has different
      requirements please change accordingly (**Settings** --> **NTP
      Settings**).
    * Add your inverter in the inverter settings (**Settings** --> **Inverter
      Settings**).

[^1]: The device always acts as an AP after booting, even if it is already
      configured as a Wi-Fi client. The AP is closed after a configurable
      timeout.
