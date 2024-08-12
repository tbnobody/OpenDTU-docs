# Flash ESP32

## Prepare

Before starting the flash process you may have to manually put the ESP into
*bootloader mode*. Most boards are able to do this automatically, but sometimes
that is not working:

1. Connect `GPIO0` to `GND` before booting the device (often there is a `BOOT` or similar button which does this when pressed)
2. Power-on or reset the ESP32 while `GPIO0` is connected to `GND`
3. Start the flash process

## Write to Flash Memory

The actual procedure to flash the ESP32 depends on the tool used. Click on the tab below that matches your flash tool.

=== "Web Flasher :material-linux::material-apple::material-microsoft-windows:"

    [OpenDTU Web Flasher](webinstall.md)

    The easiest, platform independent method. Requires Chrome based browser.

=== "ESP Flash Tools :material-microsoft-windows:"
    Espressif provides their own [Flash Download Tools](https://www.espressif.com/en/support/download/other-tools){target=_blank} for Windows.

    ![Flash Downloda Tool](../assets/images/esp_flash_tools.png)

    Change `COM9` to the correct port on your computer.

    * On startup, select Chip Type --> **ESP32** and WorkMode -> **Develop**
    * Prepare all settings (see picture). Make sure to uncheck the **DoNotChgBin** option. Otherwise you may get errors like "invalid header".
    * **Only if you want or need to start from scratch (settings are lost):** Press "Erase" button on screen. Look into the terminal window, you should see dots appear. On some boards, the automatic bootloader selection does not work. In this case you have to manually press the "Boot" button on the ESP32 board. Wait for "FINISH" to see if flashing/erasing is done.
    * To program, press "Start" on screen, then the "Boot" button (if required).
    * When flashing is complete (FINISH appears) then press the Reset button on the ESP32 board (or powercycle ) to start the OpenDTU application.

=== "esptool.py :material-linux::material-apple::material-microsoft-windows:"
    Install [esptool](https://github.com/espressif/esptool) using `pip`:

    ```sh
    python3 -m venv /path/to/your/venv
    source /path/to/your/venv/bin/activate # on Linux
    /path/to/your/venv/bin/Activate.ps1 # on Windows
    pip install esptool
    esptool version # should show esptool version
    ```

    Use esptool to write a firmware binary to your ESP32:

    ```sh
    # erase flash only if you want or need to
    # start from scratch (settings are lost):
    esptool --port COM1 erase_flash

    esptool --baud 921600 --port COM1 --chip esp32 \
        --before default_reset --after hard_reset \
        write_flash --flash_mode dout \
        --flash_freq 40m --flash_size detect \
        0x0 opendtu-generic*.factory.bin
    ```

    * Adjust the `--chip` parameter to the actual chip in use, e.g., `esp32-s3`.
    * Change `COM1` to the correct port on your computer.
    * In case you get an error at the end of the flash procedure, you can try again using a lower baudrate eg. 460800.

=== "ESP_Flasher :material-microsoft-windows:"

    Users report that [ESP_Flasher](https://github.com/Jason2866/ESP_Flasher/releases/){target=_blank} is suitable for flashing OpenDTU on Windows.
