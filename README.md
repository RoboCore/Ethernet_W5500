Ethernet W5500 Library
========
Ethernet W5500 library is made for various Open Source Hardware Platform and support WIZnet's W5100, W5200 and W5500 chip. The Ethernet library lets you connect to the Internet or a local network.

## Supported devices
* RoboCore Ethernet W5500 Shield (using W5500)
* ioShield, WIZ550io (using W5500)
* W5200 Ethernet Shield, WIZ820io (using W5200)
* Arduino Ethernet Shield (using W5100)

## Hardware
* [Ethernet W5500 Shield](https://www.robocore.net/loja/produtos/arduino-shield-ethernet-w5500.html "Ethernet W5500 Shield")
* [ioShield](http://wizwiki.net/wiki/doku.php?id=ioshield "ioShield")
* [W5200 Ethernet Shield](https://github.com/Wiznet/W5200-Ethernet-Shield "W5200 Ethernet Shield")
* [Ethernet Shield](http://arduino.cc/en/Main/ArduinoEthernetShield "Ethernet Shield")

## Software
#### 1. Install Ethernet W5500 library
##### Arduino IDE 1.0.x

Download all files and overwrite onto the "\libraries\Ethernet" folder in your project in sketch.

##### Arduino IDE 1.5.x

Download all files and replace the "\libraries\Ethernet\src" folder in your Arduino IDE. This will update the "utility" folder also under "\libraries\Ethernet\src".

#### 2. Select device: W5100, W5200 or W5500
In the W5100.h file (\libraries\Ethernet\utility\w5100.h), uncomment the device(shield) you want to use.

```cpp
#ifndef	W5100_H_INCLUDED
#define	W5100_H_INCLUDED

#include <avr/pgmspace.h>
#include <SPI.h>

typedef uint8_t SOCKET;
//#define W5100_ETHERNET_SHIELD
//#define W5200_ETHERNET_SHIELD
#define W5500_ETHERNET_SHIELD
```
By default, "WIZ550io_WITH_MACADDRESS" is commented and if you uncomment it, you can use the MAC address stored in the WIZ550io.

```cpp
#if defined(W5500_ETHERNET_SHIELD)
//#define WIZ550io_WITH_MACADDRESS // Use assigned MAC address of WIZ550io
#include "w5500.h"
#endif
```

## How to use the WIZ Ethernet library and evaluate existing Ethernet example.
All other steps are the same as the steps from the Arduino Ethernet Shield. You can find examples in the Arduino IDE, go to Files->Examples->Ethernet, open any example, then copy it to your sketch file (gr_sketch.cpp) and change configuration values properly.
After that, you can check if it is work well. For example, if you choose 'WebServer', you should change IP Address first and compile and download it. Then you can access web server page through your web browser of your PC or something.

## Revision History

#### [Wiznet](https://github.com/Wiznet/WIZ_Ethernet_Library "WIZ Ethernet Library");
* Initial Release : 14 August 2013
* Adding function to read / write W5500 PHY configuration register : 4 December 2013
* Support the Arduino Due (Arduino IDE 1.5.x). Now it support 42Mhz SPI clock ! (by Jinbuhm Kim): 28 Feb. 2014
* Separate the folder for Arduino IDE 1.0.x & Arduino IDE 1.5.x

#### Robocore
* 10/07/15
  * Forked from Wiznet;
  * Fixed memory leak in Ethernet.begin() (for multiple calls);
* 17/07/15
  * Renamed to Ethernet_v2 (to avoid conflict with standard Ethernet library);
  * Added library for IDE 1.6.5 (library folder has the same structure as 1.0.x but the files from 1.5.x must be used because of change in <IPAddress.h>).
* 27/11/15
  * Fixed bug in DNS library that wouldn't recognize correct DNS;
  * Added getRemoteIP() method to the EthernetClient class.
* 22/02/18
  * Renamed to Ethernet_W5500 (to avoid conflict with standard Ethernet library);

