# BPI R2 BSP (板子生成工具包)

總綱
------------
此工程是專門給 banana-pi R2 板子用的, 裡面包含了 U-boot 及 Linux Kernel 4.14.x.


事前準備
---------------
1. Downloading Ubuntu 16.04 image for R2 board from http://www.banana-pi.org/r2-download.html
2. Running below command to burn this image to SD card which must be larger than 8GB
```
		dd if=\<image file\> of=/dev/mmcblk0
```
3. Install this SD to R2 board
4. Press power button a few seconds to activate this board. The default baud rate of serial port is 115200, the default username/password are root/bananapi


如何編譯 U-boot 及 Linux kernel
------------------------------------------
To build this project, the following packages are required:
```
	gcc-arm-linux-gnueabihf 
	u-boot-tools
```
1. Clone this code to a host PC on which the Ubuntu 16.04 is installed
2. Run script build.sh
```
	./build.sh
```
3. Select 1 to build both uboot and kernel
4. Both new uboot and kernel will be generated in folder SD when it completes


如何更新 U-boot 及 Linux kernel
--------------------------------------------
If you don't have tools for banana-pi products, please run below commands to install them:
```
	apt-get install pv
	curl -sL https://github.com/BPI-SINOVOIP/bpi-tools/raw/master/bpi-tools | sudo -E bash
```
1. Install SD card to this host PC, please ensure Ubuntu 16.04 R2 image is installed on this SD card
2. Enter folder SD which is generated after building
3. Run below command to update u-boot and Linux kernel
```
	bpi-update -c bpi-r2.conf
```
4. After it completes, move SD to R2 board
5. Press power button to activate this board
