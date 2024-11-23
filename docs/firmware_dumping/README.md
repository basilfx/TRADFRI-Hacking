# Firmware dumping

## Requirements
To dump (or flash) firmware of a microcontroller, you have to use an external
debugger. I have used a [STK3600](https://www.silabs.com/development-tools/mcu/32-bit/efm32lg-starter-kit),
that can be configured to be an external debugger.

You can use software like [JLink](https://www.segger.com/products/debug-probes/j-link/)
or [OpenOCD](http://www.openocd.org) to flash the target.

The steps below will work for Series-1 microcontrollers (ICC-A and ICC-A-1).
The newer microcontrollers are Series-2, for which support is limited or more
expensive to get started.

### J-Link
If you use J-Link, you can use the command below to connect to the ICC-1 or
ICC-A-1 module:

```
JLink -If SWD -Speed 5000 -Device EFR32MG1PXXXF256
```

To dump the flash contents, use the command below (0x40000 is 256 KiB):

```
savebin output.bin 0x0 0x40000
```

To load a flash from file, use the following command:

```
loadbin output.bin 0x0
verifybin output.bin 0x0
```

I have confirmed that you can dump the flash, erase the device and load it
again, and the modules will still work.
