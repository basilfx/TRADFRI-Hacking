# Analysis of firmware

* [Introduction](#introduction)
* [Dumping firmware](#dumping-firmware)
* [Flash layout](#flash-layout)
* [SPI NOR flash contents](#spi-nor-flash-contents)
* [References](#references)
  * [Source files](#source-files)

## Introduction
This document describes my findings of the IKEA TRÅDFRI firmware downloaded
from the GU10 light bulb (LED1650R5). According to the binary, it contained
version 1.2.214. As of writing, this was the latest firmware available.

## Dumping firmware
See [this](../../../../docs/firmware_dumping) for more information.

## Flash layout
Inside the [strings](firmwares/ikea/led1650r5-1.2.214.strings), references are
made to certain C sources named `bootloader-interface-app.c`. This seems to
refer to Silicon Labs application note
[AN772](https://www.silabs.com/documents/public/application-notes/an772-using-legacy-application-bootloader.pdf).

This application note suggest a flash layout (figure 2.1) that looks like this:

* 0x00000 - 0x03fff -> Bootloader + recovery image (16 KiB)
* 0x04000 - 0x????? -> Application data
* 0x????? - 0x3ffff -> Simulated EEPROM

Looking at a binary map of the firmware (created using
[binvis.io](http://binvis.io)), we can clearly identify three regions, of which
the second region starts at 0x04000 and the third one at 0x3d000.

[<img src="firmwares/ikea/led1650r5-1.2.214.png" height="384">](firmwares/ikea/led1650r5-1.2.214.png)

For completeness, not that there are also the [following](https://github.com/basilfx/TRADFRI-Hacking/issues/24#issuecomment-651145045)
memory addresses:

* 0x0fe00000 - 0x0fe00800 -> user data (2 KiB)
* 0x0fe10000 - 0x0fe12800 -> factory bootloader (10 KiB)

## SPI NOR flash contents
The board provides a 2 MBit (256KiB) SPI NOR Flash. Using the
[SPI Flash Dump](firmwares/riot-os/spi_flash_dump) utility, I dumped the flash
contents.

It seems seem that the flash chip is not used for this LED bulb. When dumping
its contents, it only reads 0xFF (I have verified this utility against a known
working flash chip before using).

## References

### Source files
There are several references to C source files. Below an overview of files
encountered.

* af-main-soc.c
* association.c
* bootloader-interface-app.c
* command.c
* counters-soc.c
* cstartup-iar.c
* eeprom.c
* ember-configuration.c
* ember-multi-network-stub.c
* ember-stack-common.c
* event-control.c
* mac-arbiter.c
* mac-efr32.c
* mac-info-element-parsing-stub.c
* mac-receive.c
* mac.c
* mfg-token.c
* micro-common.c
* micro-internal.c
* neighbor.c
* network.c
* ota-storage-eeprom-page-erase.c
* ota-storage-eeprom.c
* packet-buffer.c
* packet-header.c
* pGrf4ce-stack-stubs.c
* phy-common.c
* route-discovery.c
* route-table.c
* scan.c
* sim-eeprom2-internal.c
* sim-eeprom2-internal.c
* sleep-efm32.c
* system-timer.c
* token.c
* zigbee-stack.c
