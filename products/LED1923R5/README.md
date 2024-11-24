# LED1923R5
GU10 RGB spot.

## Details

* Socket: GU10
* Potted: no
* Glued: yes (lens cover)
* TRÅDFRI Module: MGM210L22F
* Rated: 345 lm, 4.6 W

## Teardown

* [Images](products/LED1923R5/images)

## Pinout

### Module

* PA3 -> ?
* PC2 -> White channel (PWM1)
* PC3 -> Red channel (PWM2)
* PC4 -> Green channel (PWM3)
* PC5 -> Blue channel (PWM4)

## Power usage
Measured using a Voltcraft 3000 energy monitor.

| Brightness | Color      | Power (W) | Cos φ |
|------------|------------|-----------|-------|
| 100%       | Cool White | 2.4       | 0.60  |
| 50%        | Cool White | 0.4       | 0.25  |
| 10%        | Cool White | 0.3       | 0.20  |
| Off        | Cool White | 0.0       | 1.00  |

## Sources
* https://github.com/basilfx/TRADFRI-Hacking/issues/39
