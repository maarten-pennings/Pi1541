# Pi1541

Commodore 1541/1581 emulator for the Raspberry Pi

Pi1541 is a real-time, cycle exact, Commodore 1541 disk drive emulator that can run on a Raspberry Pi 3A, 3B or 3B+. The software is free and I have endeavored to make the hardware as simple and inexpensive as possible.

Pi1541 provides you with an SD card solution for using D64, G64, NIB and NBZ Commodore disk images on real Commodore 8 bit computers such as;-
Commodore 64
Commodore 128
Commodore Vic20
Commodore 16
Commodore Plus4

See https://cbm-pi1541.firebaseapp.com/ for SD card and hardware configurations.

Toolchain Installation
----------------------

On Windows use GNU Tools ARM Embedded tool chain 5.4:
https://launchpad.net/gcc-arm-embedded/5.0/5-2016-q2-update
and Make:
http://gnuwin32.sourceforge.net/packages/make.htm


On dpkg based linux systems install:
(Tested on osmc/rpi3)
```
apt-get install binutils-arm-none-eabi gcc-arm-none-eabi libnewlib-arm-none-eabi libstdc++-arm-none-eabi-newlib
```

On RHEL/Centos/Fedora systems follow the guide at:
https://web1.foxhollow.ca/?menu=centos7arm
(Tested on Centos7/x64 with GCC7)
https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads/7-2017-q4-major

Building
--------
```
make
```
This will build kernel.img


In order to build the Commodore programs from the `CBM-FileBrowser_v1.6/sources/` directory, you'll need to install the ACME cross assembler, which is available at https://github.com/meonwax/acme/


Additions in this fork
----------------------

This fork is used in my [Pi1541 project](https://github.com/maarten-pennings/pi1541device).

- Fix `warning: '__dso_handle' initialized and declared 'extern'`.
- Fix `warning: writing 1 byte into a region of size 0`.
- Fix activity LED (thanks to [Warshi7819](https://github.com/pi1541/Pi1541/issues/206#issuecomment-1162708867))
- Add support for SSD1309 based OLEDs (128x64). These are compatible with CH1116. Typically used for bigger (1.54") OLEDs.
- Added [workflow](https://github.com/maarten-pennings/Pi1541fw/blob/master/.github/workflows/compile.yaml) 
  to GitHub to build `kernel.img`.
- Step version to 1.25.


(end)