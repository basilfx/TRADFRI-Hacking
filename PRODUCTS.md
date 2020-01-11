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

### LED1650R5

Details:

* Socket: GU10
* Potted: no

Teardown:

* Use a small flat screw driver to lift up the plastic lens.

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
This seems to be the successor of the LED1650R5.

Details:

* Socket: GU10
* Potted: no
* Glued: yes (lens cover)

Teardown:

* Use a hot air gun to soften the glue that holds the lens to the glass body. Make sure that you heat it up evenly, otherwise the glass will crack. Then use a small blade to lift up the lens.

TRÅDFRI Module pinout:

* PB13 -> LED driver

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

TRÅDFRI Module (unverified):

* Time selection dial (R13): PA1 (Looks like a potentiometer between R12 high side and a FET to GND enabled directly by PB14.)
* Day/night selection dial (R15): PB15 (Dito, with resistor R14 and same transistor.)
* Pairing button (S1): Silicone rubber button puling PA0 directly to GND

* The motion detection dome is connected (one pin directly, one indirectly) to an "E93196C 5090C 9A" labelled 8-pin chip to which also PC10 and PB14 are connected (needs further investigation).

* Various test points:
  * VCC: `TP8_1`, `TP8_2`
  * GND: `TP2_1`, `TP3_2`
  * PB13: `TP2_2`
  * PA0: `TP4_1`, `TP4_2`
  * PA1: `TP5_2`

The module is easy to take apart, and debug wires can be soldered on without separating the radio / MCU PCB from the carrier PCB. The carrier board is labelled "D-Sensor-A1-01-A-V2.0".

### E1526 (Gateway)

Details:

* Power supply: USB 5V 1A

### ICTC-G-1 (Wireless dimmer)

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

### ICPSLC24-10NA (LED output controller/dimmer)

Details:

* Potted: no

The output appears to be measured by the module somehow.
Detailed PCB investigation required.

TRÅDFRI Module pinout (incomplete/unverified):

* PA0: K1 (Reset key)
* PA1: Goes to ZD1, through R9 and then to OUT+, possibly output measuring?
* PB13: Pulls down the FET Gate
* PF0: Pin 2 on header
* PF1: Pin 3 on header

### ICPSHC24-10EU-IL-1 (10W LED driver/dimmer)

10 Watt Power supply with the 24 V output being controlled by ICPSLC24-10NA

### ICPSHC24-30EU-IL-1 (30W LED driver/dimmer)

30 Watt Power supply with the 24 V output being controlled by ICPSLC24-10NA

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
