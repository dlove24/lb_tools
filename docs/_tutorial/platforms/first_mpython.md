---
title: A First Circuit in MicroPython
parent: Using the LB Development Board
nav_order: 2
---

# A First Circuit in MicroPython

## Goals

New projects in [MicroPython](https://www.raspberrypi.com/documentation/microcontrollers/micropython.html#what-is-micropython) on the [Raspberry Pi Pico](https://www.raspberrypi.com/documentation/microcontrollers/) require you to set-up the virtual environment, libraries and support tools. Visual Studio Code automates 

and the creation of a very simple circuit. This is very much the bare bones of what you need to get started: once the basic circuit is working, that should give you a base for exploring the circuits you want.

**NOTE:** This chapter is all about setting up the [Raspberry Pi Pico W](https://www.raspberrypi.com/documentation/microcontrollers/raspberry-pi-pico.html) using Python (or rather to be accurate a variant called [MicroPython](https://micropython.org/)), as it allows us to quickly prototype designs on the Pico. You can also use C/C++ with the [C SDK](https://www.raspberrypi.com/documentation/microcontrollers/c_sdk.html) to programme the [RP2040](https://www.raspberrypi.com/documentation/microcontrollers/rp2040.html) which is the microcontroller at the heart of the Pico. This involves using a compiler as discussed in the chapter on setting up the Pico with C.

## Installing MicroPython

1. The _custom_ boards we have the Pico's installed into can use the standard MicroPython firmware for the Pi Pico W (or Pi Pico if using basic Pico) to enable all of the various breakout features. The full set of releases is available on [Raspberry Pi website](https://www.raspberrypi.com/documentation/microcontrollers/micropython.html). You need to ensure you download the latest [firmware for the Pico W](https://micropython.org/download/rp2-pico-w/rp2-pico-w-latest.uf2) or [firmware for the Pico](https://micropython.org/download/rp2-pico/rp2-pico-latest.uf2). Download this file somewhere convenient.

2. Next we need to put the Pico into _bootloader mode_ so that we can install the firmware. Our _custom_ board has a `RESET` button on it so you do not need to unplug the USB cable (as described on the Raspberry Pi website). Instead hold down the `BOOTSEL` button on the Pico device (white button) then press the `RESET` button on the board --- this should mean Windows and Linux machines recognise the Pico as a USB drive and add it as either a hardrive (named `RPI-RP2`) on Windows or as a connected USB device on MAC/Linux also called `RPI-RP2`. If this doesn't happen, you may need to repeat the procedure or alternatively unplug the USB cable from the computer and hold down the `BOOTSEL` button while re plugging the USB in.

3. Copy the `.uf2` file downloaded in step 1 [^up1] to `RPI-RP2` device, and a few seconds after the copy finishes the Pico will reboot and will start the MicroPython interpreter on the Pico. It will disappear as a connected USB device at this point.

## Installing a Python IDE

We now need to talk to the Pico-W, and get to the point where we can install programs onto it. First of all create a folder (in OneDrive on Windows and in your Home directory on Linux) to put your Python code into. Then we need to make sure we have an appropriate integrated development environment (IDE) to write your code in. We are going to use Microsoft Visual Studio Code (VSCode) as a common environment --- this is used by Raspberry Pi foundation for C/C++ SDK programming. [^up4]. The steps below are how to make VScode work with micropython.

1. Microsoft [Visual Studio Code](https://code.visualstudio.com/) which is the IDE that is used for programming the Pico using the C/C++ SDK. This can be found on all engineering lab PCs. It is free and can also be installed on your own computer and comes for Windows, MAC or Linux. There is also a limited web based [client](https://vscode.dev/) which maybe useful if you want to just edit code. 

2. Before we can use VSCode we need to install some extensions so that microPython will run --- go to the extensions tab on left-hand menu ![image](/home/halliw02/git/pico_tutorial/chapters/media/extensions.png){height="4mm"} (or Ctrl-Shift-X), and search for MicroPico as shown in @fig:vscodeext. If it is not installed it will show a blue Install as highlighted in @fig:vscodeext. You will also need to ensure you have Python, Pylance and IntelliCode extensions.

![Visual Studio Code Extensions](/home/halliw02/git/pico_tutorial/chapters/media/vscodext.png){#fig:vscodeext width="85%"}

3. Now you need to open the folder you created to store your Python files in --- using File \> Open Folder. Then to ensure we are using MicroPython open the command palette on VSCode (Ctrl-Shift-P or View \> Command Palette) and select MicroPico: Configure project. Provided your Pico board is connected to PC and has been flashed with MicroPython this will open in the bottom pane the python console on the Raspberry Pi Pico as shown in @fig:console

![MicroPython Console](/home/halliw02/git/pico_tutorial/chapters/media/picoconsole.png){#fig:console}

## A Simple Circuit

This is about the simplest circuit possible, and serves as a good check that the whole tool-chain is working as expected, and that you can drive simple outputs. It is often used as the embedded systems equivalent of 'Hello World', and you will see this a number of times as we introduce different boards and/or different programming languages. 

1. Create a file in your IDE called '`blink.py`' with code as in @lst:blink, and save the file when you have finished:

```{.python .numberLines}
from machine import Pin
from utime import sleep

led = Pin("LED", Pin.OUT)
led.low()

while True:
      try:
         led.toggle()
         print("Toggle")
         sleep(1) # sleep 1sec
      except KeyboardInterrupt:
         break
led.off()
print("Finished.")
```

: `blink.py` code {#lst:blink}

2. Once you're ready to transfer the program to your Pico --- you should see the on-board LED (green light next to the USB socket) flashing. To do this, open command palette (Ctrl-Shift-P) and run the script on the Pico using MicroPico: Run current file on Pico or at the bottom of window press the Run button as shown in @fig:vscode_bot. This will be stop when the code is running which you can use to stop the code.

![VSCode bottom bar](/home/halliw02/git/pico_tutorial/chapters/media/vscodebottom.png){#fig:vscode_bot}

You can upload the file to the Pico by right clicking on file and selecting Upload file to Pico[^up5] as shown in @fig:vscode_upload.

![Upload file to Pico](/home/halliw02/git/pico_tutorial/chapters/media/vspico_upload.png){#fig:vscode_upload width="30%"}

3. Now we want to create a simple circuit on the bread-board, which attaches an LED to the ground (`GND`) on the _Custom Board_ headers via a 330$\Omega$ resistor. We need to make sure the LED is the right-way around - the long leg is connected to the anode (that is positive) and the short leg to the cathode (that is negative).

4. We need to figure out where to attach the positive leg of the LED to. First of all, we need to change line 4 in @lst:blink to be `led = Pin(2, Pin.OUT)`{.python} --- so we are now toggling `Pin 2`, or more precisely the `GPIO Pin 2` (where 'GPIO' stands for _General Purpose Input/Output_). The full diagram of the Pico looks like @fig:PicoPins and if we look we can see that `GPIO Pin 2` is also known as `GP2`, which is how you will find it marked on the _Custom Board_.

   ![The Pin Layout of the Standard Raspberry Pi Pico Board](/home/halliw02/git/pico_tutorial/chapters/media/picow_pinout.png){#fig:PicoPins width=75% }

   Like many micro-controllers, the functionality you need will depend on what you are using it for: so to save space you can select which _mode_ the pin is in, enabling different functionality when you need it. Our Pico will default to using GPIO mode: but you can adjust this if you want (and will do in later Workshops).

5. Hook up the `GP2` via a resistor to the positive leg of the LED, and make sure the negative leg is connected to `GND`, run the code and it should start to flash. If it does: congratulations, and everything is working! If not, you may need to start debugging …

   ![An Example of the Final Board Layout](/home/halliw02/git/pico_tutorial/chapters/media/final_board.jpeg){ #fig:PicoFinal width=50% }

   The final circuit should look something like @fig:PicoFinal. If not, double-check your code, and the previous steps: if in doubt ask for help.

## VS Code & Pico

It is worth that clicking on the `Toggle Pico-W-FS` on the bottom bar of VS Code as shown in @fig:vscode_bot will open the files on the Pico itself. This means in the explorer part of the VSCode window you will see a Pico (W) Remote Workspace as shown in @fig:pico_ws, which shows you what is currently on the Pico. You can download the project from the Pico by right clicking and selecting Download project from Pico --- this will put files into current open file.

![Pico (W) Remote Workspace in VS Code](/home/halliw02/git/pico_tutorial/chapters/media/vspico_workspace.png){#fig:pico_ws width="75%"}

## Next Steps

1. Try to hook up a second LED (maybe a different colour) to another pin on the Pico, and see if you can get both flashing in different sequences. This will also require some modification of the code.

2. Ask for a traffic light board which plugs into 9 pin single line socket at bottom of _Custom board_. This has 6 LEDs and two push button switches on it. The first LED (red 1) is connected to GP9, the second LED (amber 1) is connected to GP8, the third LED (green 1) is connected to GP7, the first button is connected (as a switch for ground) to GP6, the fourth LED (red 2) is connected to GP5, the fifth LED (amber 2) is connected to GP4, the sixth LED (green 2) is connected to GP3 and the second button is connected to GP2. Push this into socket.

3. The _Custom Board_ has all the GP pins broken out as male header pins and a number of sockets on it --- the four 2x6 right angle female sockets on the left-hand side are designed to work with the [Digilent Pmod interface]{https://digilent.com/reference/_media/reference/pmod/pmod-interface-specification-1_2_0.pdf} devices. SPI1 (top connector with Pin 1 being bottom of top row) follows the Pmod interface Type 2(SPI)  with Pin 1 connected to GP13 (SPI1 CS - chip select),  Pin 2 connected to GP15 (SPI1 TX which is COPI/MOSI[^up2]), Pin 3 connected to GP12 (SPI1 RX which is CIPO/MISO) and Pin 4 connected to GP14 (SPI1 SCK - serial clock) --- pins 7-10 of the Pmod are broken out for both SPiI and SPI0. SPI0[^up3] has pin 1 connected to GP18, pin 2 connected to GP16, Pin 3 connected to GP19 and Pin 4 connected to GP17 so can be used for general purpose PMods but not SPI0 other than using a software SPI as connections wrong. The two I2C ports are connected correctly for Pmod interface Type 6 with I2C0 Pin 3 connected to GP21 (I2C0 SCL) & Pin 4 to GP20 (I2C0 SDA) and I2C1 Pin 3 connected to GP11 (I2C1 SCL & Pin 4 connected to I2C1 SDA). The remaining pins for these two sockets (1,2 and 7-10) are broken out. On the bottom of the _Custom Board_ is a 9 pin female socket which takes a custom traffic light board and 2 Pmod sockets with all pins broken out. In the case of all the Pmod sockets, Pins 5 & 11 are connected to GND and Pins 6 & 12 are connected to VCC (3.3V)

[^up4]: An alternative is [Thonny](https://thonny.org) (Raspberry Pi foundation uses this in its tutorials on MicroPython) which can be installed on all operating systems and also has a portable version for Windows which does not require admin rights.
[^up5]: You can upload entire project from computer to Pico as well.
[^up1]: Latest MicroPython firmware for the Pico is `RPI_PICO-20240222-v1.22.2.uf2` and for Pico-W is `RPI_PICO_W-20240222-v1.22.2.uf2`  on 02 May 2024.
[^up2]: One modern terminology is Controller (not master) and Peripheral (not Slave) so CIPO for MISO and COPI for MOSI - but these can be read as Main In Sub Out and Main Out Sub In. There is no agreement yet fully on replacement of the historical terms of Master and Slave and indeed argument about whether they should be replaced.
[^up3]: During testing it transpired the SPI0 header was not correctly connected to the SPI0 interface pins so it cannot be directly used with SPI PMods.

