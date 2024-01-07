____
<kbd> <br> [supported-devices](./diy/supported-devices.md) <br> </kbd>
<kbd> <br> [Installation](./diy/installation-bin.md) <br> </kbd>
<kbd> <br> [Display and button Setup](./diy/display-setup.md) <br> </kbd>
<kbd> <br> [errors.md](./diy/errors.md) <br> </kbd>
<kbd> <br> [serial-commands](./usage/serial-commands.md) <br> </kbd>
<kbd> <br> [settings](./usage/settings.md) <br> </kbd>
___
## Before you continue
Using the display interface is entirely optional. You can also control the Deauther via serial or the web interface.  

We cannot start at 0 for this tutorial, so if you find this too tricky, get an Arduino starter kit with good documentation to get a feeling for tinkering with electronics. 😊

I focused on the NodeMCU in this tutorial since it is one of the most popular dev-boards. But every other ESP8266-based board should work just the same.  


## What you need
- A breadboard ([Amazon*](https://amzn.to/3HtxH9y), [AliExpress*](https://s.click.aliexpress.com/e/_DDdF6Tt))
- Jumper wires ([Amazon*](https://amzn.to/3HrKIk0), [AliExpress*](https://s.click.aliexpress.com/e/_DEEniwr))
- An ESP8266 dev board (see [Supported Devices](/docs/diy/supported-devices)) ([Amazon*](https://amzn.to/3YbdDyN), [AliExpress*](https://s.click.aliexpress.com/e/_Ddd7piL))
- At least 3 buttons (3 are required, optionally up to 6) ([Amazon*](https://amzn.to/3WdXRkI), [AliExpress*](https://s.click.aliexpress.com/e/_DDPYp0R))
- An SSD1306 or SH1106 OLED display with 128x64 pixels (other resolutions are **not** supported) ([Amazon*](https://amzn.to/3FNekar), [AliExpress*](https://s.click.aliexpress.com/e/_DB5UkwB))
- Optional: an RGB LED (3 single LEDs or a Neopixel will also work) ([Amazon*](https://amzn.to/3Pn0bDJ), [AliExpress*](https://s.click.aliexpress.com/e/_DBmkHbV))
- Optional but recommended: 2x 10k ohm resistors ([Amazon*](https://amzn.to/3PpEeEm), [AliExpress*](https://s.click.aliexpress.com/e/_DlZSG8x))
- A working Arduino IDE setup that can compile this project (see [Installation](/docs/diy/installation-arduino))


## Wire everything up
Look up the pinout references for your board. Here's one for the NodeMCU: 
![NodeMCU pinout](/img/diy/NODEMCU_DEVKIT_V1.0_PINMAP.png)

We have a limited amount of pins, and not every pin can be used for everything:

| NodeMCU Pin |  GPIO   | Note |
| ----------- | ------- | ---- |
| D0          | GPIO 16 | No I2C or PWM. Don't use this pin for the RGB LED or Display. |
| D1          | GPIO 5  | OK |
| D2          | GPIO 4  | OK |
| D3          | GPIO 0  | Connected to flash button. |
| D4          | GPIO 2  | Needs pull-up resistor.  |
| D5          | GPIO 14 | OK |
| D6          | GPIO 12 | OK |
| D7          | GPIO 13 | OK |
| D8          | GPIO 15 | Needs pull-down resistor |
| D9          | GPIO 3  | RX (Serial). Avoid this pin. |
| D10         | GPIO 1  | TX (Serial). Avoid this pin. |
| SD2         | GPIO 9  | Used for Flash. Avoid this pin in QIO mode. |
| SD3         | GPIO 10 | Used for Flash. Avoid this pin in QIO mode. |


### Buttons
Connect each button to a GPIO and GND. 
Like in this Arduino tutorial: https://www.arduino.cc/en/Tutorial/InputPullupSerial

### LED
The LED is used as an optional indicator. For example, Green = idle, Blue = scanning, and RED = deauth attack detected (when scanning).  
You can use single digital LEDs, an RGB LED, or a Neopixel LED (WS2812b).  

By default, the LED on GPIO 16 (NodeMCU onboard LED) and the LED on GPIO 2 (ESP-12 and ESP-07 on-module LED) are used.

## setup with I2C OLED


| Display | GPIO |
| ------- | ---- |
| GND | GND |
| VCC/VDD | VCC / 3.3V |
| SCL/CLK/SCK | GPIO 4 (D2) |
| SDA | GPIO 5 (D1) |

| Button | GPIO |
| ------ | ---- |
| UP | GPIO 14 (D5) |
| Down | GPIO 12 (D6) |
| A | GPIO 13 (D7) |

| NEOPIXEL LED | GPIO |
| ------ | ---- |
| GND | GND |
| VCC | VCC/3.3V |
| DIN | GPIO 15 (D8) |

| Light | GPIO |
| ------ | ---- |
| GND | GND |
| VCC | GPIO 16 (D0) |

## Testing everything


When everything is correctly set up and uploaded, open the serial monitor with Arduino (Tools > Serial Monitor). 

- **Set the baud rate to `115200` and select `Newline`.**  If you see it resetting every few seconds, check the code and make sure you didn't use the same pin twice.

- If there's no image on display, type `set display true;;save settings` and press enter. Now press the reset button on the board to restart it. If the display doesn't show anything, something is off. Check your connections and the code.  

- To test all buttons, enter `screen mode buttontest`. To get back, use `screen mode menu`.  

- To test the LED(s), you can run `led <r> <g> <b>`. For example, `led 255 0 0` should turn the LED red.   

If you still have problems with the display, try running an example to test if it's a software or a hardware problem. This is the display library used in the Deauther: https://github.com/squix78/esp8266-oled-ssd1306  
You can find examples there. Try to get those running.  
