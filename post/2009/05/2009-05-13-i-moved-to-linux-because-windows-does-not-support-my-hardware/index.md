---
title: "I moved to Linux because Windows does not support my Hardware"
date: "2009-05-13"
tags: 
  - "64bit"
  - "linux"
  - "windows"
---

Back in the days of 2005, I did not use Linux because it did not support my cheap PCTEL HSP56 Dial-up modem. Now, I do not use Windows Vista because it does not support my cheap Telson Electronics CDMA 1x USB Wireless Modem. Sorry for my poor choice of internet (both in 2005 and now) because I live in rural area of Nepal and we don't have a choice.

I tried to install driver for my PCTEL HSP56 modem by compiling the driver and even recompiling the kernel but in vain. My modem had drivers included in the CD for Windows XP and below.

My CDMA USB had driver for Windows XP and Vista, but only for 32 bit versions. I had a Windows Vista 64bit installation and my modem failed to work because 64bit drivers were not provided. I tried to search online but in vain.

I booted up Ubuntu Intrepid Ibex 64bit, my alternate OS and half-heartedly tried wvdialconf. I had very less hope based on my previous experience with winmodems but to my surprise, the modem was detected. I configured it and dialed in, and voila, I was online.

In Windows world, if a hardware has a driver for one version of Windows does not mean it works with other versions too. But in the Linux world, if your hardware runs with one distro or version almost essentially means that will run on all other distros. This proved to be true as I could run my modem with OpenSuse, Fedora, Puppy and other versions of Ubuntu as well, both 32bit and 64bit and it should work with all other distros (well, if they have a kernel with cdc acm module for my hardware).

So, however, Linux hardware support was poor and it still is for so many devices, it should change in the future and hardware incompatibility will become a Windows-Only terminology.
