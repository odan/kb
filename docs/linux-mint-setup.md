---
layout: default
title: Linux Mint Setup
published: true
parent: Linux
---

# Linux Mint Setup

## Download

* Download the latest ISO from [the Linux mint website](https://linuxmint.com/)
* Optional: Copy the ISO file with [Etcher](https://www.balena.io/etcher/) to a USB stick and install it.

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
