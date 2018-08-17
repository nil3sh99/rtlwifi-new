rtlwifi_new
===========
### A repo for the newest Realtek rtlwifi codes.

This code will build on any kernel 4.2 and newer as long as the distro has not modified
any of the kernel APIs. IF YOU RUN UBUNTU, YOU CAN BE ASSURED THAT THE APIs HAVE CHANGED.
NO, I WILL NOT MODIFY THE SOURCE FOR YOU. YOU ARE ON YOUR OWN!!!!!

It includes the following drivers:

rtl8192ce, rtl8192cu, rtl8192se, rtl8192de, rtl8188ee, rtl8192ee, rtl8723ae, rtl8723be, and rtl8821ae.

If you are looking for the driver for rtl8822be or rtl8723de, then execute the following command:

git checkout origin/extended -b extended

#### Installation instruction
You can find <<YOUR WIRELESS DRIVER CODE>> using `lspci | grep Wireless`.
Afterwards, execute the following lines of codes in your shell:  
  
```
You will need to install "make", "gcc", "kernel headers", "kernel build essentials", and "git".

If you are running Ubuntu, then

 sudo apt-get install linux-headers-generic build-essential git

Please note the first paragraph above.

Fire up the terminal and run the following commands:-

iwconfig
(#this will be used later on for setting up the wlan port)
(#check for the device name for IEEE 802.11bgn)

(#Download the zip file of this repository and extract it on desktop)

git clone git@github.com:NAAG1999/ubuntu_wifi-bug-hp-.git

