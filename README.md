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

$ iwconfig
(#this will be used later on for setting up the wlan port)
(#check for the device name for IEEE 802.11bgn)
(#Download the zip file of this repository and extract it on desktop)
				OR
($ cd Desktop
 $ mkdir <<folder name>>
 $ git clone git@github.com:NAAG1999/ubuntu_wifi-bug-hp-.git )

$ cd Desktop
$ cd rtlwifi_new-master
$ make
$ sudo make install
$ sudo modprobe -rv rtl8723be
$ sudo modprobe -v rtl8723be ant_sel=2
$ sudo ip link set wlo1 up

(#up there inplace of wlo1 enter your device name, you got from running iwconfig)
(# if you get an error of permission denied then do the following steps:-)
	$ sudo su
	(Enter the password)
	$ echo "blacklist hp_wmi" > /etc/modprobe.d/hp.conf
	$ rfkill unblock all
)

$ sudo iw dev wlp13s0 scan

To make the settings permanent,type below command in terminal and press enter.

$ echo "options rtl8723be ant_sel=2" | sudo tee /etc/modprobe.d/50-  rtl8723be.conf




