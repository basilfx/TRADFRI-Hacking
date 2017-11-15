# Introduction

The [IKEA TRÅDFRI](http://www.ikea.com/us/en/catalog/categories/departments/lighting/36812/) family of products provide you with several lighting solutions that interconnect using [ZigBee Light Link](http://www.zigbee.org/zigbee-for-developers/applicationstandards/zigbee-light-link/).

If we take a simple GU-10 light bulb, it contains:

* Power supply
* LED driver
* IKEA TRÅDFRI module

The tiny module is used in many of their products, and is actually a small piece board with some GPIO exposed. This board uses the energy-efficient Silicon Labs [EFR32MG1P132F256GM32](https://www.silabs.com/products/wireless/mesh-networking/efr32mg-mighty-gecko-zigbee-thread-soc/device.efr32mg1p132f256gm32) microcontroller, which is a ARM Cortex M4 with 256 Kb of flash.

You can take out the board, and hook it up to your own lighting solutions. Or, you can flash it with your own firmware, for other purposes.

As a proof of concept, check out [this YouTube video](https://www.youtube.com/watch?v=yi_Z2WtmdDU) I made.

## Pinout
I found a pinout on [this website](https://tradfri.blogspot.nl).

![IKEA TRÅDFRI module pinout](images/pinout.png)

## Flashing
To connect to an external JTAG/SWD debugger, connect as follows:

* PF0 -> SWCLK
* PF1 -> SWDIO
* PF2 -> SWO
* RESETn -> RESETn
* GND -> GND
* VCC -> VCC (3v3)

In my case, I could leave the module in the light bulb, but for flashing I provided my own power supply by hooking it up to the VCC line directly.

You can use software like [JLink](https://www.segger.com/products/debug-probes/j-link/) or [OpenOCD](http://www.openocd.org) to flash the target.

## Isolation
If you plan to leave the board in-place, and run your own light bulb firmware, never connect external devices (e.g. debugger or serial adapter) to a light bulb that is plugged in. Due to different voltage levels, you could destroy your devices.

If you want to connect an external device, ensure that it is properly isolated (e.g. using a optocoupler).

## Pictures

The light bulb I used:

![IKEA TRÅDFRI module pinout](images/gu10.jpg)

Front of the TRÅDFRI module:

![Back of IKEA TRÅDFRI](images/front.jpg)

Back of the TRÅDFRI module:

![Front of IKEA TRÅDFRI](images/back.jpg)

My setup (the small board is a UART isolator):

![Setup](images/setup.jpg)

## Relevant sources
I have gathered some information from the following sources:

* [IKEA Trådfri hacking](https://tradfri.blogspot.nl)
* [Trådfri: ESP8266-Lampen-Gateway](https://www.heise.de/make/artikel/Ikea-Tradfri-Anleitung-fuer-ein-ESP8266-Lampen-Gateway-3598411.html)

## License
Creative Commons BY Attribution 4.0 International
