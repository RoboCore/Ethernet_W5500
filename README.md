WIZ Ethernet Library
========
WIZ Ethernet library is made for various Opena Source Hardware Platform and support WIZnet's W5100, W5200 and W5500 chip. The Ethernet library lets you connect to the Internet or a local network

## Supported devices
* ioShield, WIZ550io (using W5500)
* W5200 Ethernet Shield, WIZ820io (using W5200)
* Arduino Ethernet Shield (using W5100)

## Hardware
* [ioShield](http://wizwiki.net/wiki/doku.php?id=ioshield "ioShield")
* [W5200 Ethernet Shield](https://github.com/Wiznet/W5200-Ethernet-Shield "W5200 Ethernet Shield")  
* [Ethernet Shield](http://arduino.cc/en/Main/ArduinoEthernetShield "Ethernet Shield")  

## Software
#### Install WIZ Ethernet library  
##### Arduino IDE 1.0.x

Download all files and overwrite onto the "\libraries\Ethernet" folder in your project in sketch.

##### Arduino IDE 1.5.x

Download all files and 1) overwrite the souce and utility folder to the "\libraries\Ethernet\examples\" folder. 

#### Select device(shield)  
In the W5100.h file(\libraries\Ethernet\utility\w5100.h), uncomment the device(shield) you want to use.  

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
By default, "WIZ550io_WITH_MACADDRESS" is commented and if you uncommnet it, you can use the MAC address stored in the WIZ550io.

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
* Initial Release : 14 August 2013
* Adding function to read / write W5500 PHY configuration register : 4 December 2013
* Support the Arduino Due (Arduino IDE 1.5.x). Now it support 42Mhz SPI clock ! (by Jinbuhm Kim): 28 Feb. 2014