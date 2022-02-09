# Canned-ERCF-board
Enraged Rabbit Carrot Feeder CAN expansion board for Duet3

Work in progress, first beta version. Do not use this one as it has issues with UART control of the TMC2209 drivers. It can only be used with STEP/DIR.

![Canned ERCF Board front first version](/img/canned-ercf-board-front.jpg)

The Canned ERCF board is a controller board made to support the [ERCF](https://github.com/EtteGit/EnragedRabbitProject) multifilament feeder system based on the [ERCF Easy Brd](https://github.com/Tircown/ERCF-easy-brd) by Tircown.

The board uses a Atmel/Microchip SAM C21 microcontroller module with USB and CAN, the [Sammy-C21](https://www.chip45.com/products/sammy-c21-1.0_atmel_smart_arm_sam_module_samc21_usb_dual_can_duet3d.php) from [Chip45](https://www.chip45.com/).

The firmware is a modified version of the [Duet3Expansion Sammy-C21 firmware](https://github.com/Duet3D/Duet3Expansion) by [Duet3D](https://www.duet3d.com/)  

As the board on which it's based upon it has:

- Two TMC2209 stepsticks Stepper motor drivers for Selector and Gear
- 24V-5V Voltage converter
- Three 3.3V signal inputs for encoders and endstops with 3.3V source.
- One 3.3V PWM output for servo control with 5V source.
- MCU Module. In this case the Atmel/Microchip SAMC21G18A based Sammy-C21

As an extension this board has CAN-support and is connected to another Duet 3 board via a CAN bus. Firmware is updated via CAN and the DWC (Duet Web Control frontend) so the USB-port is not really used.

There are two pin pairs for the CAN bus so either the CAN-bus can be terminated by closing the solder brideg on the back of the board or it can be routed to the next board in the chain,

![Canned ERCF Board rear first version](/img/canned-ercf-board-rear.jpg)

Disclaimer: This is work in progress and it's right now under development and there are issues with this version that maybe will be corrected in the next. It's based on many part over which I have no control at all. I take no responsibilty whatsoever for the functionality or safety and I claim the right to not inform about anything about this product known to me now or in the future. This is soley at your own risk and I accept no responsiblity, financially or otherwise, if it causes your controller board to break, your house to burn down, your wife to divorce you, if it simply doesn't work at all or any other scenario possible in any multiverse. If you do not accept that all responibility for use of this product is your own, please don't download, build or use it.
