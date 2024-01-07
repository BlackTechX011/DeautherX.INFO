________
<kbd> <br> [supported-devices](../diy/supported-devices.md) <br> </kbd>
<kbd> <br> [Installation](../diy/installation-bin.md) <br> </kbd>
<kbd> <br> [Display and button Setup](../diy/display-setup.md) <br> </kbd>
<kbd> <br> [errors.md](../diy/errors.md) <br> </kbd>
<kbd> <br> [serial-commands](../usage/serial-commands.md) <br> </kbd>
<kbd> <br> [settings](../usage/settings.md) <br> </kbd>
___
# DeautherX
An ESP8266_Deauther with Evil Twin attack and more

## Functions

* Scan for WiFi networks and clients
* Create docents of WiFi networks (beacon flooding)
* Confuse WiFi trackers by sending fake (probe flooding)
* Disconnect selected devices by sending (deauthentication attack)
* Create Fack SSID with Evil Twin Attack

## About this Project

This firmware allows you to easily perform a variety of actions to test 802.11 networks using an [ESP8266](https://www.espressif.com/en/products/socs/esp8266). It's also a great project for learning about WiFi, microcontrollers, Arduino, hacking and electronics/programming in general.  

The deauthentication attack is the main feature, which can be used to disconnect devices from their WiFi network.  
Although this denial-of-service attack is nothing new, a lot of devices are still vulnerable to it. Luckily this is slowly changing with more WiFi 6 enabled devices being used. But a lot of outdated WiFi devices remain in place, for example in cheap IoT hardware.
With an ESP8266 Deauther, you can easily test this attack on your 2.4GHz WiFi network/devices and see whether it's successful or not. And if it is, you know you should upgrade your network.

### Caution Disclaimer
This project is a proof of concept for testing and educational purposes.  
Neither the ESP8266, nor its SDK was meant or built for such purposes. **Bugs can occur!**  

**Use it only against your own networks and devices!**  
Please check the legal regulations in your country before using it.  
We don't take any responsibility for what you do with this program. 

________
