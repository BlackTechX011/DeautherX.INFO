---
<kbd>&nbsp;<br>&nbsp;[supported-devices](../diy/supported-devices.md)&nbsp;<br>&nbsp;</kbd>
<kbd>&nbsp;<br>&nbsp;[Installation](../diy/installation-bin.md) <br>&nbsp;</kbd>
<kbd>&nbsp;<br>&nbsp;[Display and Button Setup](../diy/display-setup.md) <br>&nbsp;</kbd>
<kbd>&nbsp;<br>&nbsp;[errors.md](../diy/errors.md) <br>&nbsp;</kbd>
<kbd>&nbsp;<br>&nbsp;[serial-commands](../usage/serial-commands.md) <br>&nbsp;</kbd>
<kbd>&nbsp;<br>&nbsp;[settings](../usage/settings.md) <br>&nbsp;</kbd>
---

The most important things first:
* Any ESP8266-based development board can run the Deauther firmware.
* ESP8285 is also supported (basically the same as ESP8266 but with internal flash).
* ESP32 is **not** supported as it's an entirely different chip.

## Recommended Boards

### NodeMCU

![NodeMCU](/img/devices/nodemcu.jpg)

The NodeMCU board is probably the most popular ESP8266 development board. It's cheap, widely available, uses the ESP12 module, and has pre-soldered header pins - which come in handy when using a breadboard.

The original NodeMCU (as seen in the picture above) uses a CP2102 USB serial chip. The NodeMCU V3 is slightly bigger and uses the CH340 chip. However, both versions work the same.

Do not buy an ESP32 version if you're planning to build a Deauther. You'll need an ESP8266!

Affiliate Links:  
[Amazon](https://amzn.to/3iYVMYu)&nbsp;
[AliExpress](https://s.click.aliexpress.com/e/_9gMH6T)

### LOLIN (WEMOS) D1 Mini

![Wemos D1 Mini](/img/devices/d1mini.jpg)

The D1 Mini is an excellent choice if the size is a concern. It's small, cheap, and supports add-ons. Like the NodeMCU, different versions of the D1 Mini are also available. Some use a bare ESP8266 SoC with the CP2102 for serial, while others have an ESP12 module and CH240 serial chip. But they practically don't make any difference in usage.

A significant pro or con, depending on your project, is that the included header pins are not pre-soldered! Therefore, you will need a soldering iron to connect sensors, buttons, or displays.

Another important note is that this board is widely known as WEMOS D1 Mini, but the original creators actually rebranded to LOLIN. Here is a link to their [Aliexpress store](https://lolin.aliexpress.com/store/1331105). The original boards might be slightly more expensive than from other AliExpress shops but also of higher quality.

Affiliate links:  
- [Amazon](https://amzn.to/3DLaBYg)
- [AliExpress](https://s.click.aliexpress.com/e/_ADk3lh)

### Adafruit Feather HUZZAH with ESP8266

![Adafruit Feather HUZZAH with ESP8266](/img/devices/featherhuzzah.jpg)

The Adafruit Feather HUZZAH is a high-quality development board with a LiPo battery charger. But not only that, the Feather board layout is a common form factor for various boards, and plenty of addons are available!

Versions with and without soldered header pins are available. 
Documentation and tutorials can be found at [learn.adafruit.com](https://learn.adafruit.com/adafruit-feather-huzzah-esp8266).

If you want an easy way to add a battery to your Deauther, this is the board for you.  
(You can flash it with the same .bin file as the NodeMCU)

- [Adafruit Product Page](https://www.adafruit.com/product/2821)
---
