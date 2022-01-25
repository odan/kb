---
layout: default
title: VirtualBox Setup
published: true
parent: Linux
---

# VirtualBox Setup

## Requirements

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## Ubuntu Server prerequisites

* Start the Ubuntu guest virtual machine
* Login to the Ubuntu guest as a sudo user and install the packages required for building external kernel modules:
* `sudo apt update`
* `sudo apt install build-essential dkms linux-headers-$(uname -r)`
* From the virtual machine menu, click Devices -> “Insert Guest Additions CD Image”.
* Mount the CD-ROM:
* `sudo mkdir -p /mnt/cdrom`
* `sudo mount /dev/cdrom /mnt/cdrom`

## Guest Extension Setup

Navigate to the mounted CD-Rom and run the `VBoxLinuxAdditions.run` 
script to install the Guest Additions.

* `cd /mnt/cdrom`
* `sudo sh ./VBoxLinuxAdditions.run --nox11`
* Reboot the Server for changes to take effect: `sudo init 6`

Read more: [How to Install VirtualBox Guest Additions on Ubuntu](https://linuxize.com/post/how-to-install-virtualbox-guest-additions-in-ubuntu/)

## Shared Folder Setup

* In the window of the running VM, you select `Device` > `Shared Folders`
* Add a new shared folder
* Enter th local path `C:\xampp\htdocs`
* Folder name: `shared`
* Read only: No
* Mount automatically: Yes
* Mount point: `/shared`
* Mount permanent: yes

Read more: <https://gist.github.com/estorgio/1d679f962e8209f8a9232f7593683265>

## Network Adapter Setup

* Open the VM settings > Network
* Change "Adapter 1" type from "NAT" to "Network Bridge"
* Click at "Extended"
* Select the adapter: "Intel PRO/1000 MT Desktop..."
* Select the mode: "Allow all and host"
* Click on "Ok" to save all settings.
* Start the VM
* Login as super-user with `sudo su`
* Enter `ifconfig` to find the local ip address, e.g. `192.168.0.172`

## Testing

On the guest VM open `http://192.168.0.172` in your browser to the hosted website.
Change the IP address as shown in `ifconfig`

Please note: When you start the VM it will take some seconds until
apache is started.
