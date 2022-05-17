# fluidterm a Serial Terminal for FluidNC

### Overview

Fluidterm is a "serial terminal" program.  Serial terminals let you interact directly with a gadget that is connected to a host computer via a serial line or USB-to-serial adapter.  Fluidter is primarily intended for use with [FluidNC](https://github.com/bdring/FluidNC) - a next generation CNC controller that runs on ESP32 hardware - but is not inherently limited to that use.

### Why Fluidterm

The normal way to interact with a CNC controller like FluidNC, Grbl or g2core is via a "GCode sender" program.  Most GCode senders are graphical UIs with point-and-click features for running CNC jobs. They are great for controlling machines after they are working.  However, when you are trying to setup a machine for the first time or when something is going wrong,  it is helpful to "cut out the middleman" (the graphical sender) and "go direct".  Most senders have a widget to send commands directly, but it is often surrounded by so many other buttons and displays that people do not know how to use it - and often it hides some of the messages unless you configure it in a special way.

There are many serial terminal programs, so why did we make another one?  Most of the existing serial terminal programs have grown to include many features that are unnecessary for the task of direct interaction with FluidNC.  That does not prevent them from doing the job, but it does make it difficult to explain how to configure for the specific task - usually involving screenshots of many graphical menus - and the explanation is different for each different program.  Furthermore, most of the existing serial terminals are platform-specific (the best cross-platform one is PuTTY, which has 31 configuration screens each with about a dozen configuration items).

We made Fluidterm so we can support a single, cross-platform, easy-to-install basic way to interact with FluidNC.  We hope that it will make FluidNC support easier by providing a baseline way to send test commands and receive diagnostic output.

### Fluidterm Ancestry

Fluidterm is an extension of a simple Python serial terminal called [miniterm](https://github.com/pyserial/pyserial/blob/master/serial/tools/miniterm.py).  We added the following features to make it more useful with FluidNC:

* Highlighting (colorizing) of FluidNC informational and error messages.
* Semi-automatic detection of suitable serial ports for FluidNC controllers
* XMODEM file transfer for uploading FluidNC config files.
* Automatic triggering of FluidNC's smart line editing feature

Fluidterm is included in FluidNC release bundles so you get it
automatically when you download a FluidNC release.

### Usage

#### Windows

The FluidNC release bundle for Windows includes a precompiled executable
"fluidterm.exe" so you do not need to install Python separately.  Just
run that executable, either by double-clicking on it or by issuing the
command **fluidterm** in a CMD or PowerShell window in folder that
contains fluidterm.exe .  For convenience, you can also invoke it via
that "fluidterm.bat" batch file in the folder with the FluidNC install
scripts.

#### Linux and MacOS

On Linux and MacOS, compiling Python programs to executable files is
tricky, so on those platforms we provide the Python source code
file "fluidterm.py", plus a shell script "fluidterm.sh" to run it
after automatically installing some libraries.

In many cases, you can simply invoke "./fluidterm.sh" in a shell
window (AKA "Terminal" window on MacOS).

On Linux, it is very likely that the system will already have a
suitable version of Python 3 installed.  For MacOS, only the most
recent versions have Python 3 preinstalled, so you might have to
install that first.  Consult the Web for how to install Python 3
on MacOS (it is pretty easy).

### Command Line Options

In most cases no parameters need to be supplied, but all miniterm parameters and hotkeys are still supported. 

Changes

- The default serial port parameters match FluidNC

  - **Baudrate**: 115200
  - **EOL**: CRLF
  - **Echo**: On

- If there is one serial port, it will attempt to use it. If there is more than one, you will be presented a list to choose from.

- There is a new Transformation to colorize FluidNC responses. It uses that by default.

- You can run it as a python script or as a [Windows exe](https://github.com/bdring/fluidterm/tree/main/dist).

### Restarting the eSP32

You can restart the ESP32 to see the boot messages with the FluidNC **$bye** command or you can toggle the DTR function to restart most ESP32 modules by doing Ctrl+T Ctrl+D twice. 

<img src="https://github.com/bdring/fluidterm/blob/main/images/screenshot_01.png" width="800" >
