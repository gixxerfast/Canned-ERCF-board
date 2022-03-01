# Canned-ERCF-board v1.0-beta2
Enraged Rabbit Carrot Feeder CAN-FD expansion board for Duet3


![Canned ERCF boards V1.0-beta2 front and back from JLCPCB](/img/canned-ercf-beta2-front-back.jpg)

![Canned ERCF Boards V1.0-beta2 from JLCPCB](/img/jlcpcb-canned-ercf-boards.jpg)

The Canned ERCF board is a general purpose Duet 3 CAN extansion board but specifically made to support the [ERCF](https://github.com/EtteGit/EnragedRabbitProject) multifilament feeder system based on the [ERCF Easy Brd](https://github.com/Tircown/ERCF-easy-brd) by Tircown.

The board uses a Atmel/Microchip SAM C21 microcontroller module with USB and CAN, the [Sammy-C21](https://www.chip45.com/products/sammy-c21-1.0_atmel_smart_arm_sam_module_samc21_usb_dual_can_duet3d.php) from [Chip45](https://www.chip45.com/).

The firmware is a modified version of the [Duet3Expansion Sammy-C21 firmware](https://github.com/Duet3D/Duet3Expansion) by [Duet3D](https://www.duet3d.com/)  

You can find the fork of the modfied Duet firmware [here](https://github.com/gixxerfast/Duet3Expansion/tree/cannedboard). As the versions are moving rapidly with the new RRF version 3.4 there's no guarantees that this will be kept in synch.

**Please note that this board will not work with the standard Duet Sammy firmware.**

The board features the following functions:

- Support for up to two TMC2209 stepsticks Stepper motor drivers with UART control
- 1500 mA 24V-5V efficient switching voltage regulator. 
- Three GPIO inputs 3.3V signal inputs that may be used for encoders and endstops with 3.3V source.
- One 3.3V PWM output for hobby micro servo control with 5V source. Note that the general advice is not to source power to the servo via the board but to have a separate 5V source.
- MCU Module. It's using the Atmel/Microchip ATSAMC21G18A based Sammy-C21 MCU-module
- Input over voltage protection up to 30V
- VIN voltage monitoring.
- Three led indicators for 3.3V, 5V and VIN (24V). Easy troubleshooting if missing a rail. 

As an extension this board has CAN-FD support and is connected to another Duet 3 board via the CAN bus. Firmware is updated via CAN and the DWC (Duet Web Control frontend) so the USB-port is not really used.

This board can be used with the Sammy-C21 Duet 3 extension board firmware together with my modified configuration file. No further modifications are required (to this date).

There's a 4.7 Kohms pullup resistor on the TX/RX UART line as the BTT TMC2209 stepsticks has a 20K ohms pulldown resistor on the same line. The Duet firmware will disable the UART line before reading and writing causing the the line to go low and therefore corrupt the UART messaging. With the 4.7 Kohms pullup resistor the line is kept high all the time and the communication can function undisturbed.

There are two pin pairs for the CAN bus so either the CAN-bus can be terminated by closing the solder brideg on the back of the board or it can be routed to the next board in the chain,

![Canned ERCF Board connected to Voron V0.1 Duet 3 mini5+ via CAN](/img/connected-canned-ercf-beta2.jpg)

## BOM
Apart from the board as specified in the KiCad files with the SMT components which I have had mounted by JLCPCB, there a number of components needed to complete the board

- 1 x Sammy-C21 ATSAMC21G18A MCU module from [Chip45](https://www.chip45.com/) or [Filastruder](https://www.filastruder.com/products/sammy-c21-v1-0-duet3d-module)
- 2 x BTT TMC2209 stepstick modules
- 1 x LMP78_05-1.5 or compatible DC-DC voltage converter
- 2 x 16 pin PCB connection headers
- 4 x 8 pin PCB connection headers
- 2 x 2 pin PCB connection headers
- 2 x 2 pin MOLEX KK254 (or equivalent) male PCB connectors
- 4 x 3 pin Molex KK254 (or equivalent) male PCB connectors
- 2 x 4 pin Molex KK254 (or equivalent) male PCB connectors
- 1 x 2 pin Phoenix 5.08 Screw connector. Part # 277-1247-ND or eqivalent



### Disclaimer 
This is work in progress and it's right now under development and there may exist issues with this version that may or may not be corrected in the next version. It's based on many parts over which I have no control over at all. I take no responsibilty whatsoever for the functionality or safety and I claim the right to not inform about anything about this product known to me now or in the future. This is soley at your own risk and I accept no responsiblity, financially or otherwise, if it causes your controller board to break, your house to burn down, your wife to divorce you, if it simply doesn't work at all or any other scenario possible in any multiverse. If you do not accept that all responibility for use of this product is your own, please don't download, build or use it.




## License - Open hardware / Open software
This project and its content is realeased under the [GPLv3 license](https://www.gnu.org/licenses/gpl-3.0.html)
