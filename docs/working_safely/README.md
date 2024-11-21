# Working safely

## Introduction
If you plan to leave the board in-place, and run your own light bulb firmware,
never connect external devices (e.g. debugger or serial adapter) to a light
bulb that is plugged in. Due to different voltage levels, you could destroy
your devices.

If you want to connect an external device, ensure that it is properly isolated
(e.g. using a optocoupler).

I have designed a board that you could use to isolate UART signals. You can
find it [here](pcbs/isolator).

### Test setup
My setup (the small board is a UART isolator):

[<img src="images/setup.jpg" alt="Test setup" width="256">](images/setup.jpg)

My safer setup, including debugger (LED is connected to same pin as it would in
the GU10 light):

[<img src="images/setup2.jpg" alt="Safer test setup" width="256">](images/setup2.jpg)

Two soldered development boards that I use nowadays:

[<img src="images/setup3.jpg" alt="Safer test setup" width="256">](images/setup3.jpg)
