---
title: "[HOWTO] Enable sound in Mac OS X Snow Leopard 10.5.x or 10.6.x running in VirtualBox"
date: "2010-12-07"
categories: 
  - "debian-linux"
  - "mac"
tags: 
  - "linux"
  - "virtualbox"
---

I have recently installed Mac OS X Snow Leopard 10.6.3 with iATKOS 3 v2 disk as guest OS in VirtualBox 3.2.12 with Debian host. After fixing the video resolution issue, I noticed that there was no sound. However, VirtualBox Forum user OmegaX has written a sound driver for Mac OS X 10.5.x and 10.6.x. It can be downloaded from [here](http://forums.virtualbox.org/viewtopic.php?f=30&t=33358). Since I don't have Xcode installed, and since I did not want to go through the hassle of installing the kext manually, I downloaded the [binary installer](http://forums.virtualbox.org/download/file.php?id=2868), unpacked it by double clicking on it and installed it. It seems to take forever, but it installs successfully. The sound is working fine after a reboot.
