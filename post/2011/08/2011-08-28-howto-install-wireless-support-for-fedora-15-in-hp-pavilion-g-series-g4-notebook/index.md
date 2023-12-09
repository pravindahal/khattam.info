---
title: "[HOWTO] Install Wireless support for Fedora 15 in HP Pavilion G Series (G4) Notebook"
date: "2011-08-28"
tags: 
  - "broadcom"
  - "fedora"
  - "hp"
  - "linux"
  - "wifi"
  - "wireless"
---

To install Wireless driver for HP Pavilion G4, I followed the instructions [here](http://fedoramobile.org/fc-wireless/broadcom-linux-sta-driver). Basically, I just connected it to the internet using a cable and here is what I did in the terminal (System Tools>Terminal):

su #enter password when prompted
sudo yum localinstall --nogpgcheck http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-stable.noarch.rpm http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-stable.noarch.rpm
yum install akmod-wl
akmods --akmod wl
modprobe wl

Then, I disconnected the cable and reboot and the Wifi started working. Hope this helps.

Hope this helps.
