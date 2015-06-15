# Boom Kernel S4 Zoom (wip)





Most of the commits are  from 

	1. https://github.com/Pafcholini/Nadia-kernel-kk_N7100XXUFND3/
	2. https://github.com/glewarne/Note2Core_v3_kernel_N710x/
How to compile:

	1. Export your toolchain path
	2. CD into kernel directory 
	3. make gc2pd_00_defconfig
	4. make or make -j n (replace 'n' with number of jobs at a time, eg: make -j 2)
	5. Unpack your stock boot.img and replace the zImage with new zImage and repack
	6. Have fun

How to export toolchain path (using .bashrc):

	1. Open terminal
	2. Type pluma ~/.bashrc or you can use gedit (eg: gedit ~/.bashrc) or anyother
	3. Add these lines to .bashrc 
			export ARCH=arm
			export CCOMPILE=$CROSS_COMPILE
			export CROSS_COMPILE=your toolchain (eg:arm-cortex_a9-linux-gnueabihf-)
			export PATH=$PATH: your toolchain loaction (eg:/home/anoopkumar/android/toolchains/arm-cortex_a9-linux-gnueabihf/bin)

How to unpack/repack boot.img 

	1. Download xiaolu's mkbootimg tool form here  https://github.com/xiaolu/mkbootimg_tools and extract it 
	2. Copy and paste stock boot.img into mkbootimg_tools folder
	3. Open terminal then cd into mkbootimg_tools folder
	4. Unpack booti.mg using this command ./mkboot boot.img boot
	5. Repalce the old zImage inside the boot folder with your new zImage 
	6. Repack boot.img uisng this command ./mkboot boot boot_new.img
