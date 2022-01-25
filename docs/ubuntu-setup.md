---
layout: default
title: Ubuntu Server Setup
published: true
parent: Linux
---

# Ubuntu Server Setup

## Installation

* Download the ISO file for [Ubuntu Server](https://ubuntu.com/download/server) (Manual server installation)
* Open VirtualBox and create a new VM with the mounted ISO file
* Install Ubuntu Server
* Restart

## Disable cloud-init

Disable cloud-init on Ubuntu Server

```
touch /etc/cloud/cloud-init.disabled
```

## Uninstall cloud-init

```
sudo dpkg-reconfigure cloud-init
sudo apt purge cloud-init
sudo apt autoremove
sudo rm -rf /etc/cloud/ && sudo rm -rf /var/lib/cloud/
sudo reboot now
```

