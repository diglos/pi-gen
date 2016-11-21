#Disclaimer

This is a fork of RPi-Distro/pi-gen repository to create an Ethereum node based on Raspbian. Please visit https://github.com/RPi-Distro/pi-gen for technical details about Raspbian customization.

#EthRaspbian

EthRaspbian is a custom Linux image for the Raspberry pi 3 that runn Geth or Parity Ethereum client as a boot service and automatically turns your Rasberrypi into an full Ethereum node

#What you need

1. Raspberry Pi 2/3 (didn't test Raspberry Pi 2 yet it but should work)
2. Micro SD Card and SD Adaptor (64GB Class 10 is recommended) 
3. Power Supply for specific Raspberrypi model
4. An ethernet cable
5. EthRaspbian Image (download link below)
6. (Optional) USB keyboard, Monitor and HDMI cable

#Install instructions for Linux

Insert the MicroSD in your SD adapter and plug it into your computer. It is recommended to umount partitions in case that you have a preformated card.

1. Download the EthRaspbian image (you can choose from Geth or Parity images):

Geth edition

http://ethraspbian.com/downloads/2016-11-18-EthRaspbian-geth-1.5.2.img-lite.img.zip

Parity edition

http://ethraspbian.com/downloads/2016-11-19-EthRaspbian-parity-1.4.4.img-lite.zip

2. Unzip it (for instance):

`unzip 2016-11-18-EthRaspbian-geth-1.5.2.img-lite.img.zip`

3. Check your MicroSD device name running:

`sudo fdisk -l`

You should see a device named `mmcblk0` or `sdd` (that matchs with the size of your card. This is a dangerous operation, be careful). For further info please visit:

https://www.raspberrypi.org/documentation/installation/installing-images/linux.md

4. Flash the MicroSD (mmcblk0 device and geth edition example example):

`sudo dd bs=1M if=2016-11-18-EthRaspbian-geth-1.5.2.img-lite.img.zip of=/dev/mmcblk0 && sync`

5. Extract the MicroSD card

You are done. Insert the MicroSD in your Raspberry and power it on. Login details (Raspbian defaults):
```
User: pi
Password: raspberry
```
It is strongly recommended to change the default password by running:

`passwd`

#Instructions for Windows

Please see:

https://www.raspberrypi.org/documentation/installation/installing-images/windows.md

#Instructions for Mac

Please see:

https://www.raspberrypi.org/documentation/installation/installing-images/mac.md

# Remarks

- you can get the current parity output by running

`sudo systemctl status parity`

- SSH service is enabled so you can easily connect to your Raspberry.
