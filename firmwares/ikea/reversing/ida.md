# Reversing tradfri binaries with IDA Pro
*for this procedure IDA __Pro__ is required.*
This document describes a procedure to open a rom dump from a tradfri device with IDA to analyse its method of operation.
## Opening the file in IDA Pro
The file should be opened in IDA as a regular binary and on the 'Load a new file' dialog the processor type should be set to 'ARM Little-endian [ARM]'. Analyses should be disabled for now as it will confuse IDA. The Arm base architecture should be set to ARMv7-M.

## Finding the entry point of the binary
The reset vector is the address thats first loaded by the MCU after it has booted. The reset vector is a 4 byte integer located as second item in the vector table at location 0x00000004.

http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.dui0553a/BABIFJFG.html

Since the MCU is little-endian the value should be read starting at location 0x00000007 and the least-significant bit should be omitted as it is an indicator for Thumb code.
> The least-significant bit of each vector must be 1, indicating that the exception handler is Thumb code, see [Thumb state](http://infocenter.arm.com/help/topic/com.arm.doc.dui0553a/CHDBIBGJ.html#BABDFBBE).
## Analysing the code
The entry point found in the previous step can be used as a starting point for the auto analyser. At the entry point the 'T' register should be set to 0x01 by selecting the address and pressing alt+g.
After this is done the entry point can now be marked as code by pressing c and analyses can be enabled to analyse the binary.
## Locating the main function
