# fluidterm a Serial Terminal for FluidNC

### Overview

This is a clone of the python [miniterm](https://github.com/pyserial/pyserial/blob/master/serial/tools/miniterm.py) with changes made for [FluidNC](https://github.com/bdring/FluidNC). FluidNC is a next generation CNC controller that runs on ESP32 hardware.

In most cases no parameters need to be supplied, but all miniterm parameters and hotkeys are still supported. 

Changes

- The default serial port parameters match FluidNC

  - **Baudrate**: 115200
  - **EOL**: CRLF
  - **Echo**: On

- If there is one serial port, it will attempt to use it. If there is more than one, you will be presented a list to choose from.

- There is a new Transformation to colorize FluidNC responses. It uses that by default.

### Installation

If you don't have Python installed, get the laytest version 3 from [python.org](https://www.python.org/). Use also need to make sure you have all the libraries. use pip install to get them.
- pip install pyserial
- pip install xmodem

The best method to get fluidterm is to use Git to clone the repositiory to your computer. You can also download the code as a zip file and extract to a folder on your computer.

### Usage

- With Python: **python fluidterm.py** from the fluidterm folder.

### Restarting the eSP32

You can restart the ESP32 to see the boot messages with the FluidNC **$bye** command or you can toggle the DTR function to restart most ESP32 modules by doing Ctrl+T Ctrl+D twice. 

<img src="https://github.com/bdring/fluidterm/blob/main/images/screenshot_01.png" width="800" >
