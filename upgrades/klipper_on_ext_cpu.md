# Is it possible? Yes, but need some hardware modifications

Video proof [here](../photo/external-cpu-concept-proof.gif), after some tests, i update this instruction with pics. 

#### ALMOST ALL ACTIONS PERFORMED IN THIS GUIDE ENTAIL LOSS OF WARRANTY, DO SO AT YOUR OWN RISK.

Through research and modifications I destroyed some parts on the motherboard and eboard, so some steps were required for me but may not be required for you. 

### STEP 1. Disabling Allwinner CPU.
You need to connect one side (marked blue) of R297 to GND. I just connect to gnd on unsoldered connector.

<img src="https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/0fbe2005-98d2-40fd-9680-3af80fbdd664" width="300" />
<img src="https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/d15508b5-2179-4b3f-8807-48be5b0bd5b8" width="270" />
 
### STEP 2. Connecting main MCU to external host.
At   this step you need to unsolder two resisotrs near board mcu (R143, R144) and solder three (RX, TX, GND) wires to connect mcu to uart of external controller. I use primitive ch341 board.

Caution: Use short cables to connect 3.3v uart. After connecting this uart to the converter, you can use long usb cables, long 3.3v uart may cause errors. 

<img src="https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/92b08289-c805-4476-99b6-87bde8c9dea8" width="300" /> 


### STEP 3. Connecting eboard to external host. 
I burned the converter chip in this step, so be extremely careful.
At this step you need to solder 3 wires to RS232 converter, as pic below.

<img src="https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/7dcf6d05-81b7-4784-9888-47104661d85e" width="300" /> 


### STEP 4. Configuring remote host.
You should have klipper, monnraker, and web-ui installed on the host. Then go to the printer settings and insert the contents of AD5M [printer.base.cfg](../software/printer.base.cfg) into the printer.cfg file. 

After installing klipper and config, u need to edit serial paths, if you use both ch341 converters, you can found it in /dev/ttyUSB*.

#### If after this step klipper sees the mainboard and eboard, congratulations, you can print. If not, follow step 5...

### STEP 5. External communication interface instead rs232.
WIP 
##### CAN UNTESTED
We PROBABLY can unsolder rs232 tranceiver, R1 and R2 to solder can tranceiver to mcu, and use rx and tx wires to transmit CAN. But we need U2C.

#### USB UNTESTED
We PROBABLY can unsolder rs232 tranceiver, R1 and R2 to connect rx and tx wires to mcu`s usb.

![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/635cdc5d-f189-490c-b9f2-a0bbffa8ac9b)

