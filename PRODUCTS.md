# List of IKEA TRÅDFRI products

* [Introduction](#introduction)
* [Lighting products](#lighting-products)
* [Accessories](#accessories)

## Introduction
This list is a collection of the IKEA TRÅDFRI products, and their relevant technical properties. Please help me to update this list.

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
* Potted: yes (#3)
* three pins measures around 28 volt when brightness full.
  

### LED1650R5

Details:

* Socket: GU10
* Potted: no

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

## Accessories

### E1524 (Remote controller)

TRÅDFRI Module pinout:

* PB15 -> Color temperature
* PB14 -> Dim -
* PC10 -> On/Off
* PB13 -> TX
* PA1 -> Dim +
* PA0 -> TouchLink button

[Source](https://www.heise.de/make/artikel/Ikea-Tradfri-Anleitung-fuer-ein-ESP8266-Lampen-Gateway-3598411.html)

### E1525 (Motion sensor)

Details:

* Battery: 2x CR2032

### E1526 (Gateway)

Details:

* Power supply: USB 5V 1A

### ICTC-G-1 (Wireless dimmer)

No details (yet).

### ICPSHC24-10EU-IL-1 (10W LED driver/dimmer)

Details:

* Potted: no

The output appears to be measured by the module somehow.
Detailed PCB investigation required.

TRÅDFRI Module pinout (incomplete/unverified):

* PA0: K1 (Reset key)
* PA1: Goes to ZD1, through R9 and then to OUT+, possibly output measuring?
* PB13: Pulls down the FET Gate
* FD0: 2
* PF1: 3

### L1529 (FLOALT 60x60)

Details:

* Potted: no

TRÅDFRI Module pinout (incomplete):

* PA0: Pulse (not very readable)
* PA1: PWM3 (not very readable)
* PB1: PWM2
* PB13: PWM1

[Source](https://tweakers.net/nieuws/135893/ikea-komt-met-leddriver-om-geintegreerde-verlichting-slim-te-maken.html)
[Source](https://imgur.com/gallery/bDTRQ)
