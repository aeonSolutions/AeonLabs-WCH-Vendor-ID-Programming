[![Telegram](https://img.shields.io/badge/join-telegram-blue.svg?style=for-the-badge)](https://t.me/+W4rVVa0_VLEzYmI0)
 [![WhatsApp](https://img.shields.io/badge/join-whatsapp-green.svg?style=for-the-badge)](https://chat.whatsapp.com/FkNC7u83kuy2QRA5sqjBVg) 
 [![Donate](https://img.shields.io/badge/donate-$-brown.svg?style=for-the-badge)](http://paypal.me/mtpsilva)
 [![Say Thanks](https://img.shields.io/badge/Say%20Thanks-!-yellow.svg?style=for-the-badge)](https://saythanks.io/to/mtpsilva)
![](https://img.shields.io/github/last-commit/aeonSolutions/aeonlabs-open-software-catalogue?style=for-the-badge)
<a href="https://trackgit.com">
<img src="https://us-central1-trackgit-analytics.cloudfunctions.net/token/ping/lgeu3mh7autbw0q1rjhl" alt="trackgit-views" />
</a>
![](https://views.whatilearened.today/views/github/aeonSolutions/aeonlabs-open-software-catalogue.svg)
[![Open Source Love svg1](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](#)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat&label=Contributions&colorA=red&colorB=black	)](#)
[<img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" data-canonical-src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="30" />](https://www.buymeacoffee.com/migueltomas)

[Open Software Catalogue](https://github.com/aeonSolutions/aeonlabs-open-software-catalogue)  >> WCH Vendor ID Programming

<p align="right">
 <a href="https://github-com.translate.goog/aeonSolutions/AeonLabs-WCH-Vendor-ID-Programming?_x_tr_sl=nl&_x_tr_tl=en&_x_tr_hl=en&_x_tr_pto=wapp">Change Language</a> <br>
Last update: 23-12-2023
</p>

# WCH Vendor ID Programming

**[CH340B Configuration Tool](https://github.com/senthilnathant/tools-ch340b-configuration)** <sup> [Aeonlabs fork](https://github.com/aeonSolutions/senthilnathant-tools-ch340b-configuration) </sup> <br>
This CH340B Configuration Utility is a .Net Framework WinForms Application made by [ENTHILNATHAN THANGAVEL](https://github.com/senthilnathant) - a configuration utility built especially for WCH (WinChipHead) USB-UART Bridge chip - CH340B. The CH340B is a USB to UART Bridge that can be used to provide the Virtual Serial Port interface through USB. <br>
With this application you can read and update the configuration data of CH340B. <br>
The configuration data such as Vendor ID, Product ID, Product Name, Serial Number can be read / modified and written to the CH340B chip. This application requires .Net Framework 4.7.2 or above.

**[Adafruit's Simple Arduino-based USB VID & PID tester](https://learn.adafruit.com/simple-arduino-based-usb-vid-and-pid-tester/lets-do-this-thing)** <br>
This is a project Adafruit uses to check incoming goods as well as QC products out of manufacturing. If you have a USB device, the chip inside has a unique VID (vendor ID) and PID (product ID). For non-programmable parts, this pair is 'fixed' by the chipset itself. For programmable parts, like a microcontroller, the VID/PID is programmed in. Basically, you can use it to check chipsets and/or whether your Flora, say, has the right bootloader installed.

``` c++
// include the library code:

#include <Wire.h>
#include <utility/Adafruit_MCP23017.h>
#include <Adafruit_RGBLCDShield.h>
#include <avrpins.h>
#include <max3421e.h>
#include <usbhost.h>
#include <usb_ch9.h>
#include <Usb.h>
#include <usbhub.h>
#include <address.h>

USB     Usb;
Adafruit_RGBLCDShield lcd = Adafruit_RGBLCDShield();


void setup () {
  Serial.begin(9600);			/* Initialize serial for status msgs */
  Serial.println(F("\nVID PID tester"));

  lcd.begin(16, 2);
  lcd.setBacklight(0x7);
  lcd.print("USB VID/PID Test");
  lcd.setCursor(0,1);
  lcd.print("Waiting for USB");
}

void loop (void) {
  
  // initialize USB
  Serial.println("USB Start");

  if (Usb.Init() == -1) {
    Serial.println("OSC did not start.");
    while (1);
  }
  Serial.println("Waiting for connection...");

  while (1) {
    Usb.Task();
  
    if( Usb.getUsbTaskState() == USB_STATE_RUNNING ) break;
  }
  uint8_t rcode = 0;
  byte num_conf = 0;

  USB_DEVICE_DESCRIPTOR buf;
  rcode = Usb.getDevDescr(1, 0, 0x12, ( uint8_t *)&buf );
  if( rcode ) {
    Serial.print("USB ERROR: "); Serial.println( rcode );
    while (1);
  }
  Serial.print("VID: 0x"); Serial.print(buf.idVendor, HEX);
  Serial.print(" PID: 0x"); Serial.println(buf.idProduct, HEX);

  lcd.clear();
  lcd.print("VID: "); lcd.print(buf.idVendor, HEX);
  lcd.setCursor(0,1);
  lcd.print("PID: "); lcd.print(buf.idProduct, HEX);
  
  Serial.println("***Done!***");
  
  while (1);
}
```


<br />
<br />


## Author

You can get in touch with me on my LinkedIn Profile:

#### Miguel Tomas

[![LinkedIn Link](https://img.shields.io/badge/Connect-Miguel--Tomas-blue.svg?logo=linkedin&longCache=true&style=social&label=Connect)](https://www.linkedin.com/in/migueltomas/)

<a href="https://stackexchange.com/users/18907312/miguel-silva"><img src="https://stackexchange.com/users/flair/18907312.png" width="208" height="58" alt="profile for Miguel Silva on Stack Exchange, a network of free, community-driven Q&amp;A sites" title="profile for Miguel Silva on Stack Exchange, a network of free, community-driven Q&amp;A sites" /></a>

<a href="https://app.userfeel.com/t/2f6cb1e0" target="_blank"><img src="https://app.userfeel.com/tester/737648/image?.png" width="257" class="no-b-lazy"></a>

You can also follow my GitHub Profile to stay updated about my latest projects: [![GitHub Follow](https://img.shields.io/badge/Connect-Miguel--Tomas-blue.svg?logo=Github&longCache=true&style=social&label=Follow)](https://github.com/aeonSolutions)

<br>

**Hire me** <br>
See [here](https://github.com/aeonSolutions/PCB-Prototyping-Catalogue/wiki/How-to-Hire-AeonLabs) how to hire AeonLabs.

<br>

### Be supportive of my dedication and work towards technology education and buy me a cup of coffee
The PCB design Files I provide here for anyone to use are free. If you like this Smart Device or use it, please consider buying me a cup of coffee, a slice of pizza or a book to help me study, eat and think new PCB design files.

<p align="center">
    <a href="https://www.buymeacoffee.com/migueltomas">
        <img height="35" src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png">
    </a>
</p>


### Make a donation on PayPal
Make a donation on PayPal and get a TAX refund*.

<p align="center">
    <a href="http://paypal.me/mtpsilva">
        <img height="35" src="https://github.com/aeonSolutions/PCB-Prototyping-Catalogue/blob/main/media/paypal_small.png">
    </a>
</p>

### Support all these open hardware projects and become a GitHub sponsor  
Liked any of my PCB KiCad Designs? Help and Support my open work to all by becoming a GitHub sponsor.

<p align="center">
    <a href="https://github.com/aeonSolutions/PCB-Prototyping-Catalogue/blob/main/become_a_sponsor/aeonlabs-github-sponsorship-agreement.docx">
        <img height="50" src="https://github.com/aeonSolutions/PCB-Prototyping-Catalogue/blob/main/media/want_to_become_a_sponsor.png">
    </a>
    <a href="https://github.com/sponsors/aeonSolutions">
        <img height="50" src="https://github.com/aeonSolutions/PCB-Prototyping-Catalogue/blob/main/media/become_a_github_sponsor.png">
    </a>
</p>

# 

### License

Before proceeding to download any of AeonLabs software solutions for open-source development and/or PCB hardware electronics development make sure you are choosing the right license for your project. See [AeonLabs Solutions for Open Hardware & Source Development](https://github.com/aeonSolutions/PCB-Prototyping-Catalogue/wiki/AeonLabs-Solutions-for-Open-Hardware-&-Source-Development) for more information. 
