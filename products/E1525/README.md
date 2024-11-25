# E1525
TRÅDFRI motion sensor.

## Details:

* Battery: 2x CR2032

## Teardown
The module is easy to take apart, and debug wires can be soldered on without
separating the radio / MCU PCB from the carrier PCB. The carrier board is
labelled "D-Sensor-A1-01-A-V2.0".

* [Images](images)
* [Schematics](schematics)

## Pinout

### Module

| Module Pin | Signal                            |
|------------|-----------------------------------|
| PA0        | Switch Input                      |
| PA1        | Timer Input (Voltage Divider)     |
| PB12       | Nothing? Has a capacitor position |
| PB13       | Photoresistor Analog              |
| PB14       | PIR Interrupt                     |
| PB15       | Day/Night Analog                  |
| PC10       | PIR Serial Connection             |

### PCB

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

## Sources

* https://www.ikea.com/us/en/manuals/tradfri-wireless-motion-sensor-white__AA-2145281-3.pdf
