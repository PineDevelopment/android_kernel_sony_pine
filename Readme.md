WHAT IS THIS?
=============

Linux Kernel source code for the devices:
* Sony XPERIA L1


BUILD INSTRUCTIONS?
===================

Specific sources are separated by releases with it's corresponding number. First, you should
clone the project:

        $ git clone -b v3.18.35 https://github.com/PineDevelopment/kernel_sony_pine.git kernel

At the same level of the "kernel" directory:

Download a prebuilt gcc

        $ git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9 -b nougat-release 

Create KERNEL_OUT dir:

        $ mkdir KERNEL_OUT 
  
Your directory tree should look like this:
* kernel
* aarch64-linux-android-4.9
* KERNEL_OUT

Finally, build the kernel according the next table of product names:

| device                    | product                 |
| --------------------------|-------------------------|
| Sony XPERIA L1            | pine                    |


        $ make -C kernel  O=../KERNEL_OUT  ARCH=arm64 CROSS_COMPILE=../aarch64-linux-android-4.9/bin/aarch64-linux-android- pine_defconfig
        $ make O=../KERNEL_OUT/ -C kernel ARCH=arm64  CROSS_COMPILE=../aarch64-linux-android-4.9/bin/aarch64-linux-android-
    
You can specify "-j CORES" argument to speed-up your compilation, example:

        $ make O=../KERNEL_OUT/ -C kernel ARCH=arm64  CROSS_COMPILE=../aarch64-linux-android-4.9/bin/aarch64-linux-android- -j 8
