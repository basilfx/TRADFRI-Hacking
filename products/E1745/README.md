# E1745
TRÅDFRI motion sensor.

## Details

* Battery: 2x CR2032

## Teardown
Module is easy to take apart with the right tools, debug wires could be
soldered on without separating the radio from the carrier PCB. The carrier
board is labelled "D-SS-X2-01-A-V2.1" and the date printed is 2018-06-05.
Tradfri module markings visible are Draco1.0_105° and 0255C.

* [Images](images)

## Pinouts

### Module
TRÅDFRI Module (unverified):

* tK1 -> Day/Night selection button
* tK2 -> Pairing button
* tK3 -> Time selection button

The motion detection dome is connected (one pin directly, one indirectly) to
an "E93196B 0940A 60A" labelled 8-pin chip. This appears to be
[Elmos E931.96](https://www.elmos.com/english/products/sensor-ics/passive-infrared/pyroelectric-sensor-signal-processor-ssp/e93196.html).

### PCB
Various test points:

* VCC: `VDD`
* GND: `GND`
* Pairing BTN: `tK2`
* Day/Night BTN: `tK1`
* Time Select BTN: `tK3`
* ???: `AL`
* ???: `ENT`
* ???: `TX1`

## Sources
* https://www.ikea.com/us/en/manuals/tradfri-motion-sensor-kit__AA-1954408-1_pub.pdf
