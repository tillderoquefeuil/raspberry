# raspberry

How to Raspberry Pi 4 with ssh access on mac (without screen and keyboard)

## setup a new Raspberry Pi 4

### required
- Download (SD Card Formatter)[https://www.sdcard.org/downloads/formatter/eula_mac/index.html]
- Download the (Raspberry OS)[https://www.raspberrypi.org/downloads/raspberry-pi-os/] you need
- Download (Etcher)[https://www.balena.io/etcher/]

### mount sd card
- Open SD Card Formatter
- Select the micro SD card, choose "Overwrite format", label the Volume "boot" and click "Format"
- Eject the micro SD card and plug it again

### install Raspberry OS
- Open balenaEtcher
- Select the unzipped img of the Raspberry OS, the micro SD card and click "Flash"
- Eject the micro SD card and plug it again

### allow SSH
- Open the volume "boot" and create an empty file named "ssh"
- Finaly eject the micro SD card

## connection the Raspberry Pi 4

### plug
- Insert the micro SD card in the Raspberry Pi
- Connect it with an ethernet cable to the router
- Connect the power cable and plug it in

### find the Raspberry Pi IP address
#### with Nmap
```diff
ifconfig | grep "inet " | grep -Fv 127.0.0.1 | awk '{print $2}'
# 192.168.0.20
sudo nmap -sn 192.168.0.0/24
```


