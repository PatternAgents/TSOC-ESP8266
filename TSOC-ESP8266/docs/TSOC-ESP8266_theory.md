# TSOC-ESP8266 Theory of Operation

**TSOC-ESP8266** is a self contained, Embedded Wi-Fi Module, with integated Li-Po battery control and charging.

**TSOC-ESP8266** includes an ESP8266 Wi-Fi module, 
along with an [PCA8575 I/O Expander](http://www.nxp.com/documents/data_sheet/PCA8575.pdf) 
to provide an additional 16 Input/Output pins for the thingSoC Standard Socket,
and a Color RGB LED for USER status, with additonal, individual LEDS for Battery Charger Status and USB Status.

[![thingSoC TSOC-ESP8266](http://patternagents.github.io/img/projects/TSOC-ESP8266/TSOC-ESP8266_top.png)  
*TSOC-ESP8266*](https://github.com/PatternAgents/TSOC-ESP8266/)

* [Supported by the Arduino IDE](https://www.arduino.cc/) 
* [Wi-Fi and Over the Air Program Upgrade/Download](https://github.com/esp8266/Arduino/blob/master/doc/ota_updates/ota_updates.md)
* [thingSoC Compliant Module](http://www.thingsoc.com)
* [Mikrobus Compatible Module](http://www.mikroe.com/mikrobus/) 
* [ESP8266 Wi-Fi Module 802.11 b/g/n](https://github.com/esp8266/Arduino/blob/master/doc/reference.md#table-of-contents)
* [RGB Color LED for status](http://media.digikey.com/pdf/Data%20Sheets/CREE%20Power/CLV1A-FKB_Rev5.pdf)
* [PCA8575 I/O Expander for 16 additional GPIO lines](http://www.nxp.com/documents/data_sheet/PCA8575.pdf)
* [Analog Multiplexor and 3.3 Volt Analog Input Conditioning](https://www.fairchildsemi.com/datasheets/NC/NC7SZ157.pdf)
* [Integrated 3.7 Volt Li-Po Battery Input and Charger](http://www.microchip.com/wwwproducts/Devices.aspx?dDocName=en024903)
* [Integrated USB programming Interface, supporting the NodeMCU programming protocol](http://www.cypress.com/file/139881/download)
* [High Speed (1mB) USB Upload Capability](http://www.cypress.com/file/139881/download)
* [USB 2.1 BCD-Battery Charger Detect Protocol Compatibility](http://www.cypress.com/file/139881/download)
* [Arduino IDE Board Manager Support](https://github.com/PatternAgents/Arduino_Boards)
* +19.5dBm output power in 802.11b mode
* Wi-Fi Direct (P2P), soft-AP
* Integrated TCP/IP protocol stack
* Internal Antenna and U.FL external Antenna Support

---------------------------------------

## Theory of Operation <a name="theory_index"/>

The **TSOC-ESP8266** was designed to support either USB powered operation and/or battery powered operation.

![Schematic Page A](https://raw.githubusercontent.com/PatternAgents/TSOC-ESP8266/master/TSOC-ESP8266/docs/images/sch_page_1.png "Schematic Page A")

![Schematic Page B](https://raw.githubusercontent.com/PatternAgents/TSOC-ESP8266/master/TSOC-ESP8266/docs/images/sch_page_2.png "Schematic Page B")

![Schematic Page C](https://raw.githubusercontent.com/PatternAgents/TSOC-ESP8266/master/TSOC-ESP8266/docs/images/sch_page_3.png "Schematic Page C")

![Schematic Page D](https://raw.githubusercontent.com/PatternAgents/TSOC-ESP8266/master/TSOC-ESP8266/docs/images/sch_page_4.png "Schematic Page D")

---------------------------------------

## Documentation Index <a name="documentation_index"/>

[TSOC-ESP8266 Quick Start Guide](TSOC-ESP8266_qsg.md)

[TSOC-ESP8266 Getting Started Guide](TSOC-ESP8266_ug.md)

[TSOC-ESP8266 Theory of Operation](TSOC-ESP8266_theory.md)

[For ESP8266 Documentation, esp. IDE/toolchain](https://github.com/esp8266/Arduino)

[thingSoC Organization Website](http://thingSoC.github.io)

[thingSoC FAQ - Frequently Asked Questions](http://thingsoc.github.io/support/faq.html)

---------------------------------------

[![Image](http://thingsoc.github.io/img/projects/thingSoC/thingSoC_thumb.png?raw=true)  
*thingSoC*](http://thingsoc.github.io) 
 
