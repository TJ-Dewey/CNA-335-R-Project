# CNA 335 Rπ Project: WiFi Scanner

## STATEMENT OF WORK
simple wifi-network scanner. To satisfy the code portion of the project, I plan to have the scanner create a dictionary of visible networks, with a flag if there are any new networks from the last time it checked.

## Sources
https://www.hackster.io/amir-pournasserian/wi-fi-device-scanner-w-raspberry-pi-639ddc

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





© 2021 GitHub, Inc.
