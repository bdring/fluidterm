# fluidterm a Serial Terminal for FluidNC

### Overview

This is a clone of the python miniterm with changes made for [FluidNC](https://github.com/bdring/FluidNC). FluidNC is a next generation CNC controller that runs on ESP32 hardware.

In most case no parameters need to be supplied.

Changes

- The default serial port parameter match FluidNC

  - Baud: 115200
  - EOL: CRLF
  - Echo: On

- If there is one serial port, it will attempt to use it. If there is more than one, you will be present a list to choose from.

- There is a new Transformation to colorize FluidNC responses.

- You can run it as a python script or as a [Windows exe](https://github.com/bdring/fluidterm/tree/main/dist).

### Usage

- With Python: **python fluidterm.py**
- Windows: double click on **fluidterm.exe** 


<img src="https://github.com/bdring/fluidterm/blob/main/images/screenshot_01.png" width="800" >
