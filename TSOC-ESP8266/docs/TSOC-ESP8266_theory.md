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

The **TSOC-ESP8266** supports a single "thingSoC" socket with 3.3 Volt Level signaling.
It was designed to support both USB powered/tethered operation,
as well as 3.7 Volt single cell Li-Po battery powered operation.

### Page A : USB Connector, Battery Connector and Power Supply<a name="PAGEA"/>

Q1, a [FDC6420C](https://www.fairchildsemi.com/datasheets/FD/FDC6420C.pdf) , is a complementary (N-Channel and P-Channel) power MOSFET 
used to select between [USB Power](https://en.wikipedia.org/wiki/USB#USB_Power_Delivery) and an external 3.7 Volt single-cell 
[Li-Po battery](https://en.wikipedia.org/wiki/Lithium_polymer_battery) as the primary power input. 
[Resistor, R6 is used to "pull-down" the GATE of Q1P, turning it on, and enabling the battery (VBAT) to apply power to U2 (VIN).
If USB1 is connected and power is provided to USB1_VBUS, then Resistor R4 powers the GATE of Q1N, turning it on (and turning Q1P off...),
enabling USB1_VBUS to apply power to U2 (VIN).

U2, a [NCP361](http://www.onsemi.com/pub_link/Collateral/NCP361-D.PDF) , is a USB VBUS protection device, with an error output flag to indicate
an undervoltage, overvoltage, or overcurrent condition. The !5V0_FAULT (error flag) signal is active low, 
and is used to disable U5, the 3.3 Volt reulator. U5 a [MIC5219](http://www.micrel.com/_PDF/mic5219.pdf) Low DropOut Regualtor (LDO),
is used to provide the 3.3 Volt power rail. The power protection scheme is much faster (5/1000 of a second) more efficient than chemical
or resetable fuses, such as the PPTC fuse normally used for USB power on the typical Arduino board.

U1, a [MCP73831](http://www.microchip.com/wwwproducts/en/en024903) , is a tiny 500mA linear battery charger, used to charge the battery when
USB1 is connected and power is provided to USB1_VBUS. Battery Charger U1 is only enabled after USB enumeration and ower arbitration by the 
BCD0 (Battery Charger Detect) signal, coming from the U4, the USB-UART interface device.

![Schematic Page A](https://raw.githubusercontent.com/PatternAgents/TSOC-ESP8266/master/TSOC-ESP8266/docs/images/sch_page_1.png "Schematic Page A")

### Page B : <a name="PAGEB"/>

![Schematic Page B](https://raw.githubusercontent.com/PatternAgents/TSOC-ESP8266/master/TSOC-ESP8266/docs/images/sch_page_2.png "Schematic Page B")

### Page C <a name="PAGEC"/>

![Schematic Page C](https://raw.githubusercontent.com/PatternAgents/TSOC-ESP8266/master/TSOC-ESP8266/docs/images/sch_page_3.png "Schematic Page C")

### Page D <a name="PAGED"/>

![Schematic Page D](https://raw.githubusercontent.com/PatternAgents/TSOC-ESP8266/master/TSOC-ESP8266/docs/images/sch_page_4.png "Schematic Page D")

---------------------------------------

## Documentation Index <a name="documentation_index"/>

[TSOC-ESP8266 Quick Start Guide](https://github.com/PatternAgents/TSOC-ESP8266/blob/master/TSOC-ESP8266/docs/TSOC-ESP8266_qsg.md)

[TSOC-ESP8266 User Guide](https://github.com/PatternAgents/TSOC-ESP8266/blob/master/TSOC-ESP8266/docs/TSOC-ESP8266_ug.md)

[TSOC-ESP8266 Theory of Operation](https://github.com/PatternAgents/TSOC-ESP8266/blob/master/TSOC-ESP8266/docs/TSOC-ESP8266_theory.md)

[thingSoC Organization Website](http://thingSoC.github.io)

[thingSoC FAQ - Frequently Asked Questions](http://thingsoc.github.io/support/faq.html)

[ESP8266 Community](https://github.com/esp8266/Arduino)

---------------------------------------

[![Image](http://thingsoc.github.io/img/projects/thingSoC/thingSoC_thumb.png?raw=true)  
*thingSoC*](http://thingsoc.github.io) 
 
