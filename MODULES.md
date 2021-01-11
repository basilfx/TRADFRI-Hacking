# Modules

## ICC-1 and ICC-A-1
The ICC-1 is the first module used by many of the first TRÅDFRI products.

In January 2020 I bought the successor of the cheapest TRÅDFRI LED bulb (the
LED1837R5) and it contains an updated module (ICC-A-1). It looks like some
components have been moved, but all the part numbers look the same. I have
included updated pictures in the [Pictures](#pictures) section.

The only difference I have found (so far), is that PF3 is no longer an output
pin, but used to enable the SPI NOR Flash.

### Components
Both modules use the same energy-efficient microcontroller manufactured by
Silicon Labs. It is an EFR32 Mighty Gecko (Series 1), based around an ARM Cortex M4 with
256 KiB of flash and 32 KiB of memory.

I have been able to identify the following parts:

* Microcontroller: [EFR32MG1P132F256GM32](https://www.silabs.com/wireless/zigbee/efr32mg1-series-1-socs/device.efr32mg1p132f256gm32)
* 2 Mbit SPI NOR Flash: [IS25LQ020B](http://www.issi.com/WW/pdf/25LQ025B-512B-010B-020B-040B.pdf)
* Crystal: 38.4 MHz

I am very certain that the SPI NOR Flash component is correct. The original
firmware contains strings that refer to the exact part number. However, it also
contains references to other SPI flash components, so your module may contain
another one. The JEDEC ID it responds with is `9d 40 12`.

### Pinout
The pinout of both modules is very similar.

[<img src="images/icc-1.png" alt="Back of IKEA TRÅDFRI module (ICC-1)" width="384">](images/icc-1.png)
[<img src="images/icc-a-1.png" alt="Back of IKEA TRÅDFRI module (ICC-A-1)" width="384">](images/icc-a-1.png)

[Marco van Nieuwenhoven](https://diystuff.nl/tradfri/tradfri-zigbee-light-link-module/)
has provided a very detailed teardown of the ICC-1 module. He traced most of
the copper traces and created a schematics on his website.

### JTAG
To connect to an external JTAG/SWD debugger, connect as follows:

* PF0 -> SWCLK
* PF1 -> SWDIO
* PF2 -> SWO
* RESETn -> RESETn
* GND -> GND
* VCC -> VCC (3V3)

In my case, I could leave the module in the light bulb, but for flashing I
provided my own power supply by hooking it up to the VCC line directly.

### Pictures
I have extracted modules from the LED1650R5 (ICC-1) and the LED1837R5 (ICC-A-1).

Front of two TRÅDFRI modules:

[<img src="images/icc-1-front.jpg" alt="Front of IKEA TRÅDFRI module (ICC-1)" width="384">](images/icc-1-front.jpg)
[<img src="images/icc-a-1-front.jpg" alt="Front of IKEA TRÅDFRI module (ICC-A-1)" width="384">](images/icc-a-front.jpg)

Back of two TRÅDFRI modules:

[<img src="images/icc-1-back.jpg" alt="Back of IKEA TRÅDFRI module (ICC-1)" width="384">](images/icc-1-back.jpg)
[<img src="images/icc-a-1-back.jpg" alt="Back of IKEA TRÅDFRI module (ICC-A-1)" width="384">](images/icc-a-1-back.jpg)

## MGM210L
Another module variant was identified by @CableCatDK in [issue 39](https://github.com/basilfx/TRADFRI-Hacking/issues/39).
This module seems to be an off-the-shelve module not specifically designed for
IKEA TRÅDFRI.

### Components
An energy-efficient microcontroller manufactured by Silicon Labs is used on
this board. It is an EFR32 Mighty Gecko (Series 2), based around an
ARM Cortex M33 with 1024 KiB of flash and 96 KiB of memory.

* Microcontroller: [EFR32MG21A010F1024IM32](https://www.silabs.com/wireless/zigbee/efr32mg21-series-2-socs/device.efr32mg21a010f1024im32)
* Crystal: 38.4 MHz

Contrary to the previous generation of modules, this board does not have a
SPI NOR flash chip.

### Pinout
A pinout can be in the [user manual](https://www.silabs.com/documents/public/data-sheets/mgm210l-datasheet.pdf).

### Flashing using JTAG
To connect to an external JTAG/SWD debugger, connect as follows:

* PA1 -> SWCLK
* PA2 -> SWDIO
* PA3 -> SWO
* RESETn -> RESETn
* GND -> GND
* VCC -> VCC (3V3)

### Pictures
Front the TRÅDFRI module:

[<img src="images/mgm210l-front.jpg" alt="Back of IKEA TRÅDFRI module (ICC-1)" width="384">](images/mgm210l-front.jpg)

Back of the TRÅDFRI module:

[<img src="images/mgm210l-back.jpg" alt="Back of IKEA TRÅDFRI module (ICC-1)" width="384">](images/mgm210l-back.jpg)
