# Troubleshooting

* First: When there is no light on the solar panels, the inverter completely turns off and does not answer to OpenDTU! So if you assembled your OpenDTU in the evening, wait until tomorrow.
* When there is no data received from the inverter(s) - try to reduce the distance between the OpenDTU and the inverter (e.g. move it to the window towards the roof). If the distance is already very small (less than 1 meter), try increasing the distance.
* At **Settings** --> **DTU** you can increase the transmit power "PA level". Default is "minimum". If the distance to the inverter is small, try **de**creasing the transmit power.
* The NRF24L01+ needs relatively much current. With bad power supply (and especially bad cables!) a 10 µF capacitor soldered directly to the NRF24L01+ board connector brings more stability (pin 1+2 are the power supply). Note the polarity of the capacitor.
* You can try to use a USB power supply with 1 A or more instead of connecting the ESP32 to the computer.
* Try a different USB cable. Once again, a stable power source is important. Some USB cables are made of much plastic and very little copper inside.
* Double check that you have a radio module NRF24L01+ with a plus sign at the end. NRF24L01 module without the plus are not compatible with this project.
* There is no possibility of auto-discovering the inverters. Double check you have entered the serial numbers of the inverters correctly.
* OpenDTU needs access to a working NTP server to get the current date & time.
* If your problem persists, check the  [Issues on GitHub](https://github.com/tbnobody/OpenDTU/issues){target=_blank}. Please inspect not only the open issues, also the closed issues contain useful information.
* Another source of information are the [Discussions](https://github.com/tbnobody/OpenDTU/discussions/){target=_blank}
* Make sure to connect one inverter only to one DTU (Original, Ahoy, OpenDTU doesn't make a difference). If you query the same inverter from multiple DTUs you will mess up the communication.
