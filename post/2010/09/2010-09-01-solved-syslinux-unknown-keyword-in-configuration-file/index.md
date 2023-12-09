---
title: "[SOLVED] SYSLINUX - Unknown keyword in configuration file"
date: "2010-09-01"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "syslinux"
  - "usb-creator-gtk"
---

UPDATE: See the comments below for additional help regarding the issue.

I created a bootable USB pen drive with Ubuntu 10.10 Maverick Meerkat Alpha Daily Build on it using Startup Disk Creator (usb-creator-gtk) in Ubuntu 10.04 Lucid Lynx. This gave the following message during startup:

> SYSLINUX 3.63 Debian-2008-07-15 EBIOS Copyright (c) 1994-2008 H. Peter Anvin  
> Unknown keyword in configuration file  
> boot:

It seemed the version of syslinux in Lucid has a bug. I removed syslinux via Synaptic (which also removes usb-creator-gtk and usb-creator-common) and downloaded the deb files for the latest version of syslinux and syslinux-common from [here](http://mirrors.kernel.org/ubuntu/pool/main/s/syslinux/) and installed them. Then I installed usb-creator-gtk and then built the Live USB again. Then, it booted fine without problems.
