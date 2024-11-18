# BADRING Water leakage sensor (E2202)

Powered by a single AAA cell, boosted to 3.0V by the onboard DC-DC converter. The inner plastic retainer is held with plastic clips, which makes the device very easy to disassemble.

Teardown images can be found with FCC ID FHO-E2202.

## Hardware info

- U1: EFR32MG21A010F1024IM32
- Q1: 2N3904
- Q2: 2N3904
- Q3: Si2301

## Pinout

- PA00 PIN2 (input, driven by Q2)
- PA01 CLK (test pad)
- PA02 TMS (test pad)
- PA03 S1 (button, with pull-up)
- PA05 LED+
- PA06 VBAT
- PB00 Buzzer (driven by Q1)
- PD01 TX (test pad)
- PD00 RX (test pad)
- PD04 PIN1 (output, driven by Q3)

## Notes

The device is sending out some pulses on PIN1 and listening for a signal on PIN2. Frequency is unknown, voltage is the same as VCC (3.0V). The chip is locked, mass erase is required to load your own code to it.
