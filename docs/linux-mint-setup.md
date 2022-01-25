---
layout: default
title: Linux Mint Setup
published: true
parent: Linux
---

# Linux Mint Setup

## Download

* Download the latest ISO from [the Linux mint website](https://linuxmint.com/)
* Optional: Copy the ISO file with [E](https://www.balena.io/etcher/) to a USB stick and install it.

## Install Virtualbox guest extension

* From the virtual machine menu, click `Devices` -> `Insert Guest Additions CD Image`.
* Open the terminal and enter:
* `cd /media/user/VBox_GAs_6.1.26/`
* `sudo sh ./VBoxLinuxAdditions.run --nox11`  
* Reboot the VM for changes to take effect: `sudo init 6`

## System Updates

Update all Packages

```
sudo apt update
```

Update only security updates

```
sudo apt install unattended-upgrades
```

Upgrade the Linux system

```
sudo apt upgrade
```

Upgrade the Linux distribution

```
sudo apt dist-upgrade
```

## BIOS

```
sudo apt install intel-microcode
```
