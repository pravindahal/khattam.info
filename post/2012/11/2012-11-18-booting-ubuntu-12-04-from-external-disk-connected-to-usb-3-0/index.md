---
title: "Booting Ubuntu 12.04 from external disk connected to USB 3.0"
date: "2012-11-18"
categories: 
  - "precise-pangolin-12-04"
  - "ubuntu-linux"
tags: 
  - "linux"
---

I have a Ubuntu 12.04 install on an external HDD. On my Dell Laptop, I tried to boot into 12.04 by connecting the USB 3.0 compatible external HDD to USB 3.0 port but it wouldn't show the grub (v2.00-7ubuntu11) boot screen. A rather silly workaround helped, however. I connected it first to a USB 2.0 port so that the grub screen loaded. Then, I disconnected the HDD and reconnected it to USB 3.0 port and voila. I don't know if it's the BIOS or grub (or both?) but this is what I'm going to do from now on. :)
