# Dorsal Stream

### Overview:


## Supported Devices:


## Installing and Setup:
```
git clone <repository name>
```
*Download Arm Embedded Toolchain [here](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)
*Follow the README instructions to install arm-none-eabi-gcc in gcc-arm-none-eabi/share/doc/readme
*Verify the installation by "arm-none-eabi-gcc --version" command
*Modify the path of TOOLCAHIN_PREFIX in scripts/ARM_EABI_TOOLCHAIN.mk 
*Also modify arm-none-eabi-gcc path in scripts/Makefile 

## Run applications
*shell 1
```
cd dorsalstreamapplications/helloworldfreertos
make
```
*shell 2
```
cd dorsalstream/dist
./axtool.exe -t nu_maker -f2 ../applications/helloworld.freertos/bin/Numaker_PFM_M2351/helloworld.freertos.bin <COM num> 
#read README and change Com port number like COM1, COM2 etc..
```



#### Special thanks to RIOT
