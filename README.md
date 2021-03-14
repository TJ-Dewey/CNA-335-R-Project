# CNA 335 Rπ Project: WiFi Scanner

## STATEMENT OF WORK
simple wifi-network scanner. To satisfy the code portion of the project, I plan to have the scanner create a dictionary of visible networks, with a flag if there are any new networks from the last time it checked.

## Sources
https://www.hackster.io/amir-pournasserian/wi-fi-device-scanner-w-raspberry-pi-639ddc
https://www.cellstream.com/reference-reading/tipsandtricks/410-3-ways-to-put-your-wi-fi-interface-in-monitor-mode-in-linux

# Directions
## Step 1: Enable Pi to support mononitor mode
Change directories
```
$ cd /usr/local/src
```
Download the current version of the Re4son kernel
```
$ sudo wget  -O re4son-kernel_current.tar.xz https://re4son-kernel.com/download/re4son-kernel-current/
```
Use the tar command to extract the file
```
$ sudo tar -xJf re4son-kernel_current.tar.xz
```
Change directories
```
cd re4son-kernel_4*
```
Install the firmwaare
```
$ ./install.sh
```
## Step 2: Test for Monitor Mode
Create a monitor interface
```
$ sudo iw phy phy0 interface add mon0 type monitor  
$ iw dev
```
Check that the interface exists
```
$ ifconfig mon0 up
```


## Holdup. Alternate Instruction
Having a Panda PAU005 Wireless Dongole, I was able to skip steps 1 and 2, *negating the need for the re4son kernel* (?) by setting the dongole interface to montitor mode. Referesher on how to do this was found on the CellStream, Inc. website linked above.
```
iw dev
```
should reveal basic info about the interface, which should be wlan1
```
sudo ip link set wlan1 down
sudo iw wlan1 set monitor none
sudo ip link set wlan1 up
```
checking again will show that type has changed to monitor
```
iw dev
```


© 2021 GitHub, Inc.
