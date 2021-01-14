# List of IKEA TRÅDFRI products

* [Introduction](#introduction)
* [Product overview](#product-overview)
* [Lighting products](#lighting-products)
  * [LED1545G12](#led1545g12)
  * [LED1546G12](#led1546g12)
  * [LED1622G12](#led1622g12)
  * [LED1623G12](#led1623g12)
  * [LED1624G9](#led1624g9)
  * [LED1536G5](#led1536g5)
  * [LED1537R6](#led1537r6)
  * [LED1650R5](#led1650r5)
  * [LED1837R5](#led1837r5)
  * [LED1923R5](#led1923r5)
* [Accessories](#accessories)
  * [E1524](#e1524)
  * [E1525](#e1525)
  * [E1745](#e1745)
  * [E1526](#e1526)
  * [ICTC-G-1](#ictc-g-1)
  * [ICPSLC24-10NA](#icpslc24-10na)
  * [ICPSHC24-10EU-IL-1](#icpshc24-10eu-il-1)
  * [ICPSHC24-30EU-IL-1](#icpshc24-30eu-il-1)
  * [L1529](#l1529)

## Introduction
This list is a collection of the IKEA TRÅDFRI products, and their relevant
technical properties. Please help me to update this list.

Always work safe: never work on a mains-powered product when it is still
plugged in. I cannot be held liable for incomplete or inaccurate information,
or any damage to yourself or your products.

## Product overview
IKEA has following products and product categories for the Smart Home series
(also called TRADFRI):

 Name   | Product ID | data | comment
:------ | ---------- | ---- | :-------
Smart Home Gateway         | [E1526](#e1526) | USB 5V 1A | Ethernet gateway, An overview of the COAP protocol used by the gateway can be found [here](https://github.com/glenndehaan/ikea-tradfri-coap-docs).
FLOALT 30x30 (light panel) | L1527           | 670 lm , 12.5 W  |
FLOALT 60x60 (light panel) | [L1529](#l1529) | 2800 lm, 34 W  |
FLOALT 30x90 (light panel) | L1528           | 2200 lm, 29 W  |
GUNNARP (ceiling/wall lamp) |
LEPTITER (spotlight) |
IRSTA  (worktop lighting) |
OMLOPP (spotlight) |
STRÖMLINJE (worktop lighting) |
SKYDRAG (worktop lighting) |
FYRTUR / KADRYL (window blinds) |
5-button remote control | [E1524](#e1524) | CR2032 | (old)
5-button remote control | E1810 | CR2032 |
2-button dimmer/switch  | E1743 | CR2032 |
Wheel dimmer | | CR2032 |
Shortcut button | | CR2032 |
Motion detector | | 2x CR2032 | (old) 
Motion detector | [E1745](#e1745) | 2x CR2032
Signal repeater + battery charger | E1746 | USB 5V 1A |
Switching outlet plug/mains | E1603 |
Switching outlet plug/mains | E1703 |
LED driver 10 W with 3 connections | [ICPSHC24-10EU-IL-1](#icpshc24-10eu-il-1) | PWM 24 V (out) | Module: ICPSLC24-10NA. [Images](teardowns/ICPSHC24-10EU-IL-1/images/)
LED driver 30 W with 9 connections | [ICPSHC24-30EU-IL-1](#icpshc24-30eu-il-1) | PWM 24 V (out) | Module: ICPSLC24-10NA. [Images](teardowns/ICPSHC24-30EU-IL-1/images/)
Bulb E27 1000 lm white/warmwhite | LED1732G11 | 11 W
Bulb E27 800 lm warmwhite | LED1836G9 | 8.9 W 
Bulb E27 800 lm white/warmwhite transparent| LED1736G9 | 9.0 W 
Bulb E27 600 lm color | [LED1624G9](#led1624g9) | 8.6 W
Bulb E14 600 lm color |
Bulb E14 600 lm white/warmwhite |
Bulb E27 250 lm filament gold | LED1842G3 | 2.7 W
Bulb GU10 400 lm warmwhite |
Bulb GU10 400 lm white/warmwhite |
Bulb GU10 350 lm color | [LED1923R5](#led1923r5) | 4.6 W | Module: MGM210L22F


Standby power consumption is typically 0.5 W.

## Lighting products

### LED1545G12

Details:

* Socket: E27
* Potted: likely

### LED1546G12

Details:

* Socket: E27
* Potted: likely

### LED1622G12

Details:

* Socket: E27
* Potted: likely

### LED1623G12

Details:

* Socket: E27
* Potted: likely

### LED1624G9

Details:

* Socket: E27
* Potted: likely

### LED1536G5

Details:

* Socket: E14
* Potted: likely

### LED1537R6

Details:

* Socket: GU10
* Potted: yes

Teardown:

The potting material can be easily removed. It does not stick and will crumble
in smaller peaces once you remove it.

[Images](teardowns/LED1537R6/images)

Bulb pinout:

* 1: Common (+ max 28.4V @ 100%)
* 2: Warm leds (-)
* 3: Cold leds (-)

### LED1650R5
GU10 LED.

Details:

* Socket: GU10
* Potted: no
* TRÅDFRI Module: ICC-1

Teardown:

Use a small flat screw driver to lift up the plastic lens.

[Images](teardowns/LED1650R5/images)

TRÅDFRI Module pinout:

* PA1 -> unused (but soldered)
* PB13 -> LED driver

Power usage:

| Brightness | Power (W) | Cos φ |
|------------|-----------|-------|
| 100%       | 6.0       | 0.80  |
| 50%        | 1.6       | 0.62  |
| 10%        | 0.7       | 0.40  |
| Off        | 0.0       | 1.00  |

Measured using a Voltcraft 3000 energy monitor.

### LED1837R5
GU10 LED. This seems to be the successor of the LED1650R5.

Details:

* Socket: GU10
* Potted: no
* Glued: yes (lens cover)
* TRÅDFRI Module: ICC-A-1

Teardown:

Use a hot air gun to soften the glue that holds the lens to the glass body.
Make sure that you heat it up evenly, otherwise the glass will crack. Then use
a small blade to lift up the lens (which has small hooks as well).

You can also heat it up in an oven to heat it up evenly. I tried 150 degrees
Celsius with success.

The LED PCB can be removed by removing the two screws and lifting it up with a
square hook or similar. The heatspreader is glued with white glue (thermal
paste?) to the glass housing. I removed it by re-inserting the screw and then
lifting it with pliers. Do this carefully, or you might cut yourself (been
there, done that).

The PCB is press-fitted into the GU10 pins. To remove the whole PCB, use a side
cutter and carefully clamp perpendicular to the dots on the GU10 pins (don't
try to cut them!). A little pressure makes it then possible to lift the PCB
from the GU10 pins.

[Images](teardowns/LED1837R5/images)

TRÅDFRI Module pinout:

* PB13 -> LED driver

### LED1923R5
GU10 RGB spot.

Details:

* Socket: GU10
* Potted: no
* Glued: yes (lens cover)
* TRÅDFRI Module: MGM210L22F
* Rated: 345 lm, 4.6 W

Teardown:

See [LED1837R5](#led1837r5).

[Images](teardowns/LED1923R5/images)

TRÅDFRI Module pinout:

* PA3 -> ?
* PC2 -> White channel (PWM1)
* PC3 -> Red channel (PWM2)
* PC4 -> Green channel (PWM3)
* PC5 -> Blue channel (PWM4)

Power usage:

| Brightness | Color      | Power (W) | Cos φ |
|------------|------------|-----------|-------|
| 100%       | Cool White | 2.4       | 0.60  |
| 50%        | Cool White | 0.4       | 0.25  |
| 10%        | Cool White | 0.3       | 0.20  |
| Off        | Cool White | 0.0       | 1.00  |

Measured using a Voltcraft 3000 energy monitor.

[Source](https://github.com/basilfx/TRADFRI-Hacking/issues/39)

## Accessories

### E1524
Remote controller.

TRÅDFRI Module pinout:

* PB15 -> Color temperature
* PB14 -> Dim -
* PC10 -> On/Off
* PB13 -> TX
* PA1 -> Dim +
* PA0 -> TouchLink button

[Source](https://www.heise.de/make/artikel/Ikea-Tradfri-Anleitung-fuer-ein-ESP8266-Lampen-Gateway-3598411.html)

### E1525
Motion Sensor.

Details:

* Battery: 2x CR2032

Teardown:

The module is easy to take apart, and debug wires can be soldered on without
separating the radio / MCU PCB from the carrier PCB. The carrier board is
labelled "D-Sensor-A1-01-A-V2.0".

[Images](teardowns/E1525/images/)
[Schematics](teardowns/E1525/schematics/)

TRÅDFRI Module:

| Module Pin | Signal                            |
|------------|-----------------------------------|
| PA0        | Switch Input                      |
| PA1        | Timer Input (Voltage Divider)     |
| PB12       | Nothing? Has a capacitor position |
| PB13       | Photoresistor Analog              |
| PB14       | PIR Interrupt                     |
| PB15       | Day/Night Analog                  |
| PC10       | PIR Serial Connection             |

| Test Point | Signal                           |
|------------|----------------------------------|
| TP1_X      | Day/Night Potentiometer Analog   |
| TP2_X      | Photoresistor Analog Output      |
| TP3_X      | Ground                           |
| TP4_X      | Switch Output                    |
| TP5_X      | Timer Potentiometer Analog       |
| TP7_X      | LED                              |
| TP8_X      | Power Supply                     |

* Time selection dial (R13): PA1 (Looks like a potentiometer between R12 high
  side and a FET to GND enabled directly by PB14.)
* Day/night selection dial (R15): PB15 (Dito, with resistor R14 and same
  transistor.)
* Pairing button (S1): Silicone rubber button puling PA0 directly to GND

The motion detection dome is connected (one pin directly, one indirectly) to
an "E93196C 5090C 9A" labelled 8-pin chip to which also PC10 and PB14 are
connected (needs further investigation).

### E1745
Motion sensor.

Details:

* Battery: 2x CR2032

Teardown:

Module is easy to take apart with the right tools, debug wires could be
soldered on without separating the radio from the carrier PCB. The carrier
board is labelled "D-SS-X2-01-A-V2.1" and the date printed is 2018-06-05.
Tradfri module markings visible are Draco1.0_105° and 0255C.

[Images](teardowns/E1745/images/)

TRÅDFRI Module (unverified):

* tK1 -> Day/Night selection button
* tK2 -> Pairing button
* tK3 -> Time selection button

The motion detection dome is connected (one pin directly, one indirectly) to
an "E93196B 0940A 60A" labelled 8-pin chip. This appears to be
[Elmos E931.96](https://www.elmos.com/english/products/sensor-ics/passive-infrared/pyroelectric-sensor-signal-processor-ssp/e93196.html).

* Various test points:
  * VCC: `VDD`
  * GND: `GND`
  * Pairing BTN: `tK2`
  * Day/Night BTN: `tK1`
  * Time Select BTN: `tK3`
  * ???: `AL`
  * ???: `ENT`
  * ???: `TX1`

### E1526
Ethernet gateway.

Details:

* Power supply: USB 5V 1A

Protocol:

An overview of the COAP protocol used by the gateway can be found
[here](https://github.com/glenndehaan/ikea-tradfri-coap-docs).

### ICTC-G-1
Wireless dimmer.

Teardown:

[Schematics](teardowns/ICTC-G-1/schematics/)

Pinout:

* A0  - LED ON     - TP7
* A1  - BTN        - TP6
* B11 - FLASH CS
* B12 - GYRO INT
* B13 - FLASH VCC
* B14 - ACC INT    - TP8
* B15 - GYRO ON    - TP9
* C10 - I2C SDA
* C11 - I2C SCL
* D13 - FLASH MCLK
* D14 - FLASH MISO
* D15 - FLASH MOSI
* F0  - SWCLK      - TP1
* F1  - SWDIO      - TP2
* F2  - SWO        - TP3
* F3  - DBG        - TP4
*       RESET      - TP5

### ICPSLC24-10NA
LED output controller/dimmer

Details:

* Potted: no

The output appears to be measured by the module somehow.

Teardown:

[Images](teardowns/ICPSLC24-10NA/images/)
[Schematics](teardowns/ICPSLC24-10NA/schematics/)

TRÅDFRI Module pinout (incomplete/unverified):

* PA0: K1 (Reset key)
* PA1: Goes to ZD1, through R9 and then to OUT+, possibly output measuring?
* PB13: Pulls down the FET Gate
* PF0: Pin 2 on header
* PF1: Pin 3 on header

### ICPSHC24-10EU-IL-1
10 Watt Power supply with the 24 V output being controlled by ICPSLC24-10NA.

Teardown:

[Images](teardowns/ICPSHC24-10EU-IL-1/images/)

### ICPSHC24-30EU-IL-1
30 Watt Power supply with the 24 V output being controlled by ICPSLC24-10NA.

Teardown:

[Images](teardowns/ICPSHC24-30EU-IL-1/images/)

### L1529
FLOALT 60x60

Details:

* Potted: no

TRÅDFRI Module pinout (incomplete):

* PA0: Pulse (not very readable)
* PA1: PWM3 (not very readable)
* PB1: PWM2
* PB13: PWM1

[Source](https://tweakers.net/nieuws/135893/ikea-komt-met-leddriver-om-geintegreerde-verlichting-slim-te-maken.html)
[Source](https://imgur.com/gallery/bDTRQ)
