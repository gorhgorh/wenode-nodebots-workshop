# The Path to rx/tx

> do microcontroller dreams about serial connection ?

To control Arduinos and other microcontrollers (MCU), serial connection is often used.  
It need some libraries specifically compiled for your environment, it is easy to do but could require huge downloads if you don't already have the required tools.

this document is here to provide you a safe journey to your nodebot training 

## Prerequisite

#### software

these are the minimal software requirement needed to compile serial-port for node.

- <a href='http://nodejs.org/'>node.js <a/>
- <a hrer='https://www.python.org/download/releases/2.7.3#download'>Python 2.7</a> (NOT Python 3)
- GCC toolchain
-  <a href="http://arduino.cc/en/Guide/windows#toc4">arduino drivers</a> (windows only)
- <a href="http://gort.io/documentation/getting_started/downloads/">gort</a> or <a href="http://arduino.cc/en/main/software">Arduino IDE</a>

GCC toolchain : utilities for compiling C/C++ code each OS has it own.  
The following section will point to the major OS ones. 

**Windows :**

<a href="http://www.microsoft.com/visualstudio/eng/2013-downloads#d-2013-express">Visual Studio Express 2013 for Windows Desktop.</a>

**Osx :**

- Xcode (app store)
- Xcode command line tools (xcode pref pane, download section)

**Linux :** 

```sudo apt-get install build-essential```


to check that everything is in place :

```node -v``` should output ``` v0.x.x``` where x is the ver number.  
``` python -V``` should output ``` Python 2.7.x``` ...  
```make -v``` should output ```GNU Make x.x.x``` ...  

If you don't have an arduino yet, you are good to go. 

If you are curious, you can make the [Nodebots workshop](https://github.com/tableflip/nodebot-workshop) to familiarise with [Johnny five](https://github.com/rwaldron/johnny-five).

#### Arduino

to expose the Arduino functionalities over serial port we will use an arduino sketch called 
Firmata, to install it we can use 2 methods

*note :* Windows user should have installed arduino drivers at this point.

**A) Gort**

gort is a shell script used for uploading firmwares/sketches to various mc to use it :
 

````
cd path/to/gortFolder
./gort 
````
gort script name will differ depending your platform/proc.

to interact with Arduinos it uses AVRDUDE, to install it ````./gort arduino install```` 

```./gort scan serial``` scans your serial port and list connected devices.  

With the Arduino unplugged make a first scan, then plug the Arduino and rescan, the new device in the list is your  Arduino. 
to upload firmata 

```gort arduino upload firmata [port]``` ([port] is the arduino id found with the scan.)

**B) using arduino IDE** 

Plug the arduino in a usb port, than open the arduino IDE. 
Ensure that you selected your arduino type and port (TOOLS>Boards and TOOLS>port)

Open Files > Examples > Firmata > StandardFirmata, then upload it (the button with an arrow in the IDE or File > Upload).

Your arduino is ready !

## Testing time

To ensure that every thing works smoothly let's install the nodebot-workshop 

``` npm install -g nodebot-workshop ```.

It will compile serial port for your computer and help you discovering [Johnny five](https://github.com/rwaldron/johnny-five)

have fun and welcome to the Nodebots world