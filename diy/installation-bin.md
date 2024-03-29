---

<div align="center">
    <kbd>
        <br>
        <a href="../diy/supported-devices.md">supported-devices</a>
        <br>
    </kbd>
    <kbd>
        <br>
        <a href="../diy/installation-bin.md">Installation</a>
        <br>
    </kbd>
    <kbd>
        <br>
        <a href="../diy/display-setup.md">Display and button Setup</a>
        <br>
    </kbd>
    <kbd>
        <br>
        <a href="../diy/errors.md">errors.md</a>
        <br>
    </kbd>
    <kbd>
        <br>
        <a href="../usage/serial-commands.md">serial-commands</a>
        <br>
    </kbd>
    <kbd>
        <br>
        <a href="../usage/settings.md">settings</a>
        <br>
    </kbd>
</div>

---

1. Get a .bin file for your board from [deautherX GitHub](https://github.com/BlackTechX011/DeautherX)
2. Open NodeMCU Flasher Tool
3. Connect your ESP8266 board via USB
4. Click Connect and select the serial port of your ESP
5. Select your Deauther .bin file in `config` Tab
6. Click Flash

## Finding the correct port

If you don't know which serial port to select, open the Flasher tool and then plug in your board. Whatever port pops up in the list is what you're looking for.

You should check the cable and USB port if no new port pops up. 
Some USB cables are only for charging and cannot transmit data. 

Or maybe you're missing the drivers for your device:

- CH340/CH341 Drivers: [http://www.wch-ic.com/downloads/CH341SER_ZIP.html](http://www.wch-ic.com/downloads/CH341SER_ZIP.html)  
- CP210x Drivers: [https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)  
- FTDI Drivers: [https://ftdichip.com/drivers/](https://ftdichip.com/drivers/)

## Alternative Tools

NodeMCU Flasher tool is not the only software you can use to flash your ESP8266: 
- [esptool](https://github.com/espressif/esptool)
- [ESP flash download tools](https://www.espressif.com/en/support/download/other-tools)
- [esptool-gui](https://github.com/Rodmg/esptool-gui)

---
