# E2013
PARASOLL door/window sensor.

## Details

### Battery
This sensor runs off a 1.2 or 1.5 AAA battery, which increases the size of the
sensor.

When connecting it to a 3V power supply, it does work. It might be possible
that the DC-DC converter can be omitted in this case. However, the hall-effect
sensor emits a higher voltage level that represents a closed state.

## Teardown
* [Images](images)

## Parts
* R1 - 1 M
* R2 - 1 M
* R3 - 100 k
* R7 - 200
* R12 - 0

* U1 - EFR32MG24B020F1536IM40 (microcontroller)
* U2 - ? (hall-effect sensor)
* U3 - OC6811 (DC-DC converter)

* Y1 - 39 Mhz

## Sources
* https://www.ikea.com/us/en/manuals/parasoll-sensor-puerta-ventana-inteligente-blanco__AA-2426062-2-2.pdf
* https://fcc.report/FCC-ID/FHO-E2013/
