# Hacking IKEA TRÅDFRI

  * [Introduction](#introduction)
  * [TRÅDFRI modules](#tr-dfri-modules)
  * [Firmware analysis](#firmware-analysis)
  * [Development](#development)
  * [Other hacks](#other-hacks)
    * [EZSP Zigbee coordinator](#ezsp-zigbee-coordinator)
    * [ZigBee router](#zigbee-router)
    * [FLOALT brightness hack](#floalt-brightness-hack)
  * [Working safely](#working-safely)
    * [Test setup](#test-setup)
  * [Sources](#sources)
  * [License](#license)
  * [Disclaimer](#disclaimer)

## Introduction
The [IKEA TRÅDFRI](http://www.ikea.com/us/en/catalog/categories/departments/lighting/36812/)
family of products provide you with several home automation solutions that
interconnect using [ZigBee Light Link](http://www.zigbee.org/zigbee-for-developers/applicationstandards/zigbee-light-link/).
While the line-up initially only included lighting products, it includes power
switches and wireless window blinds as well.

Many of the TRÅDFRI are quite simple. For instance, if we take a simple light
bulb, it contains:

* Power supply
* LED driver
* IKEA TRÅDFRI module

The IKEA TRÅDFRI module is used in many of their products, and is actually
a small piece of circuit board with a few GPIO pins exposed. These pins are
then used to control the LED driver.

You can take out the board, and hook it up to your own lighting solutions. Or,
you can flash it with your [own firmware](#custom-firmware), for other purposes.

To find relevant products, I have compiled a list of IKEA TRÅDFRI products in
[PRODUCTS.md](PRODUCTS.md) (please help me to update this list). Several
products have been opened up. Teardown pictures can be found in the
[teardowns](teardowns/) folder.

## TRÅDFRI modules
So far, a few variations of the TRÅDFRI modules have been identified. They are
all using microcontrollers manufactured by Silicon Labs. The modules that have
been identified are:

* ICC-1
* ICC-A-1
* MGM210L

[<img src="images/icc-1-front.jpg" alt="Front of IKEA TRÅDFRI module (ICC-1)" width="256">](images/icc-1-front.jpg)
[<img src="images/icc-a-1-front.jpg" alt="Front of IKEA TRÅDFRI module (ICC-A-1)" width="256">](images/icc-a-1-front.jpg)
[<img src="images/mgm210l-front.jpg" alt="Front of IKEA TRÅDFRI module (MGM210L)" width="256">](images/mgm210l-front.jpg)

Some other products, such as the line-up of remote controls, have a dedicated
circuit board that integrate a microcontroller directly (i.e. no separate
module board).

More details and pictures on these modules can be found in [MODULES.md](MODULES.md).

## Firmware analysis
An analysis of some firmware versions encountered can be found in
[FIRMWARE.md](FIRMWARE.md).

## Development
The ICC-1 and ICC-A-1 have a regular Cortex M4 and the MGM210L has a
Cortex M33. These architectures are very common, and you can easily flash it
with your a custom firmware. I've added some firmwares in the
[firmwares](firmwares/) folder.

As a starting point for your own firmwar, you could take a look at
[this pull request](https://github.com/RIOT-OS/RIOT/pull/8047) for RIOT-OS. As
a proof of concept, check out [this YouTube video](https://www.youtube.com/watch?v=yi_Z2WtmdDU)
I made. In that video, I show how I control the LED connected via a serial
console.

To get access to development tools for Silicon Labs, you can take a look at
[Simplicity Studio](https://www.silabs.com/developers/simplicity-studio).

## Other hacks
Some people have came up with alternative uses for the TRÅDFRI modules. Here
are a few

### EZSP Zigbee coordinator
It is possible to load the Silicon Labs EmberZNet Zigbee coordinator firmware
on an ICC-1 or ICC-A-1. This allows you to use the module to set-up your own
ZigBee network.

MattWestb has provided a guide and firmware [here](https://github.com/MattWestb/IKEA-TRADFRI-ICC-A-1-Module).

### ZigBee router
Several users have [modified](https://community.home-assistant.io/t/sonoff-zbbridge-sonoff-zigbee-bridge-from-itead/187346/88)
the TRÅDFRI routers to improve the performance, by adding an external antenna.

This applies to the ICC-A-1 modules only, but it should be very interesting
if a the TRÅDFRI routers will use the newer MGM210L modules, because they offer
a solder pad for an external antenna.

### FLOALT brightness hack
[zw](https://github.com/zw) has patched the firmware of his FLOALT LED panel to
have an improved range of brightness levels. A guide to perform the firmware
patch has been contributed [here](https://github.com/zw/TRADFRI-Hacking/tree/master/hacks/L1527).

## Working safely
If you plan to leave the board in-place, and run your own light bulb firmware,
never connect external devices (e.g. debugger or serial adapter) to a light
bulb that is plugged in. Due to different voltage levels, you could destroy
your devices.

If you want to connect an external device, ensure that it is properly isolated
(e.g. using a optocoupler).

I have designed a board that you could use to isolate UART signals. You can
find it [here](pcbs/isolator).

### Test setup
My setup (the small board is a UART isolator):

[<img src="images/setup.jpg" alt="Test setup" width="256">](images/setup.jpg)

My safer setup, including debugger (LED is connected to same pin as it would in
the GU10 light):

[<img src="images/setup2.jpg" alt="Safer test setup" width="256">](images/setup2.jpg)

Two soldered development boards that I use nowadays:

[<img src="images/setup3.jpg" alt="Safer test setup" width="256">](images/setup3.jpg)

## Sources
I have gathered some information from the following sources:

* [IKEA Trådfri hacking](https://tradfri.blogspot.nl)
* [Trådfri: ESP8266-Lampen-Gateway](https://www.heise.de/make/artikel/Ikea-Tradfri-Anleitung-fuer-ein-ESP8266-Lampen-Gateway-3598411.html)
* [Trådfri Zigbee Light Link module](https://diystuff.nl/tradfri/tradfri-zigbee-light-link-module)
* [Trådfri Wall switch](https://wiki.iptables.dk/TR%C3%85DFRI_wall_switch)

## License
Creative Commons BY Attribution 4.0 International

## Disclaimer
This page and its content is not affiliated with IKEA of Sweden AB.

The purpose of this project is to learn and improve using reverse engineering
techniques. Use this information on your own risk.
