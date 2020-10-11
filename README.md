# raspberry

How to Raspberry Pi 4 with ssh access on mac (without screen and keyboard)
- [source](https://www.tomshardware.com/reviews/raspberry-pi-headless-setup-how-to,6028.html)

## SET A NEW RASPBERRY PI 4

### required
- Download [Raspberry Pi Imager](https://www.raspberrypi.org/downloads/)

### format sd card
- Open Disk Utility
- Erase Sd card with Format *ExFAT* and Scheme *Master Boot Record*
- [source](https://kb-eu.sandisk.com/app/answers/detail/a_id/203/kw/format)

### raspberry pi os
- Open Raspberry Pi Imager and flash the Raspberry Pi OS you want to your SD card
- You can now eject your SD card and plug it into your raspberry

### allow SSH
- Open the volume "boot" and create an empty file named "ssh"
- Finaly eject the micro SD card

### start the raspberry
- Insert the micro SD card in the Raspberry Pi
- Connect it with an ethernet cable to the router
- Connect the power cable and plug it in


## RASPBERRY TO WEB SERVER

### connection to the SSH server
```diff
# Get Ip Address
ipconfig getifaddr en0
# ***.***.*.20

# List device on network
sudo nmap -sn *.*.*.0/24
# [...]
# Nmap scan report for *.*.*.27
# Host is up (0.0069s latency).
# MAC Address: *:*:*:*:*:* (Raspberry Pi Trading)
# [...]

# Connect with SSH
ssh pi@*.*.*.27
# On first connection, you will see a security/authenticity warning. Type 'yes' to continue
# Next you will be prompted for the password for the pi login: the default password on Raspberry Pi OS is 'raspberry'
```

- [source 1: IP address](https://medium.com/@smartsplash/getting-ip-address-in-mac-b7e999149d89)
- [source 2: List device with nmap](https://linux.die.net/man/1/nmap)
- [source 3: SSH connection](https://www.raspberrypi.org/documentation/remote-access/ip-address.md)