# Dorsal Stream

### Overview:


## Supported Devices:
|Device         |Model                              |Interface|Details                                 |
|----------     |-----------------------------      |---      |----------------------------------------|
|LCD            |Adnet LCD                          |I2C      |ASM2 Board
|EEPROM         |AT24CM01, AT24CM02                 |I2C      |         
|SPI FLASH      |n25q128a13m, mx25l12805d, gd25q128 |SPI      |fatfilesystem, littlefilesystem, mtd
|KSE(SmartCard) |KSE2.1, KSE2.0                     |ISO7816  |keypair_21, keypair_20  


## Installing and Setup:
```
git clone <repository name>
```
* Download Arm Embedded Toolchain [here](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)
* Follow the README instructions to install arm-none-eabi-gcc in **gcc-arm-none-eabi/share/doc/gcc-arm-none-eabi/readme**
* Verify the installation by "arm-none-eabi-gcc --version" command
* Modify the path of TOOLCAHIN_PREFIX in **dorsalstream/scripts/ARM_EABI_TOOLCHAIN.mk** 
* Also modify arm-none-eabi-gcc path in **dorsalstream/scripts/Makefile** 
```
dorsalstream/
  scripts/
    Makefile
    ARM_EABI_TOOLCHAIN.mk
```  

## Run applications
* **shell 1**
```
cd dorsalstream/applications/helloworldfreertos
make
```
If you run "make" command, complier starts compiling. 
When compiling ends, upload binary file on board. (example uses M2351 board)
Output file comes out here, bin folder.
```
dorsalstream/
  applications/
    helloworld.freertos/
      board/
        bin
```

* **shell 2**
```
cd dorsalstream/dist
./axtool.exe -t nu_maker -f2 ../applications/helloworld.freertos/bin/Numaker_PFM_M2351/helloworld.freertos.bin <COMnum> 
# read README and change COMnum to yours like COM1, COM2 etc..
```
With the output command "reset the board", press reset button on board and connect to serial.  


### Header file include errors
If you see errors in including header files, please change the path.
For example, `#include "at.h" -> "\<path\>/include/at.h"` etc..
```
dorsalstream/
  drivers/
    esp8266/
      include/
        esp8266.h
    at/
      include/
        at.h
```  




#### Special thanks to RIOT
