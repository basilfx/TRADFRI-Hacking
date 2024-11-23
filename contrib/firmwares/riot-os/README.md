# RIOT-OS firmwares
Applications for ICC-1 and ICC-A-1 TRÅDFRI modules using RIOT-OS

## Introduction
[RIOT-OS](https://github.com/RIOT-OS/RIOT) is a real-time operating systems for
microcontrollers.

Support for the TRÅDFRI was added to RIOT-OS for the multiple reasons.

When this project started, support for EFM32/EFR32 series was just added. The
original TRÅDFRI module (ICC-A) was very similar to existing boards, so adding
support was [relativeley](https://github.com/RIOT-OS/RIOT/pull/8047) easy.

Secondly, having a decent OS with many drives made it easy to interact with
the module and drivers. This was much easier than writing all from scratch.

Lastly, RIOT-OS is very suitable for wireless connectivity, most notably
IEEE 802.15.4. Since ZigBee builds on top of this, having support for very
cheap and capable boards made it an interesting target as well. Unfortunatley,
the wireless drivers for EFR32 have not been [contributed](https://github.com/RIOT-OS/RIOT/issues/8569),
yet.

## Contents
* default - pre-compiled binary of the [default](https://github.com/RIOT-OS/RIOT/tree/master/examples/default)
  RIOT-OS application, demonstrating many of its default features.
* spi_flash_dump - application to dump the SPI flash contents
* spi_flash_identify - application to identify the SPI flash chip using it
  JEDEC flash identifier.
