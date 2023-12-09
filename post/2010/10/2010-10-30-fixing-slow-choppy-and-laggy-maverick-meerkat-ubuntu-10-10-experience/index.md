---
title: "Fixing Slow, Choppy and Laggy Maverick Meerkat (Ubuntu 10.10)"
date: "2010-10-30"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "2-6-35"
  - "2-6-36"
  - "choppy"
  - "jerky"
  - "kernel"
  - "laggy"
  - "linux"
  - "linux-mint"
  - "mainline"
  - "slow"
  - "synaptic"
---

A lot of Ubuntu 10.10 users have been complaining about Maverick being [too slow](http://ubuntuforums.org/showthread.php?t=1592245), typing becoming laggy and video performance being choppy.   Here are few things you can try to make it fast again. These have been collected from the user experience discussed in [this post in Ubuntu forums](http://ubuntuforums.org/showthread.php?t=1592245).

**Update your kernel to latest Mainline kernel**

Ubuntu Maverick Meerkat uses version 2.6.35 of Linux Kernel. A lot of users have solved their problems by upgrading to version 2.6.36. You can do so by downloading the deb files and installing them from the Ubuntu Kernel Mainline PPA: [http://kernel.ubuntu.com/~kernel-ppa/mainline/](http://kernel.ubuntu.com/~kernel-ppa/mainline/) Open the latest version that is available (rc8 is the latest in the time of writing this, however only 64bit is available, if you have 32-bit, use rc7) and download the following files: linux-headers-VERSION\_all.deb linux-headers-VERSION-generic\_VERSION\_amd64.deb linux-image-VERSION-generic\_VERSION\_amd64.deb

If you have 32bit, choose the ones that contain i386 instead of amd64 in the name. Install them one by one in the same order as listed above and reboot.

Note that if that does not help and if you want to switch back to 2.6.35 kernel again, you can always remove 2.6.36 kernel from Synaptic Package Manager (Alt+F2>gksu synaptic). Also note that you will not get updates to 2.6.36 even if newer versions are out, so you should update manually later if you find newer versions of 2.6.36 kernels.

**Clean install**

If upgrading the kernel doesn't help you, you may want to clean install in case you have upgraded from previous versions. That may not help most of you, but still might. If you have installed 64-bit version, you may even want to switch to 32bit version as many users have reported to have no problems with 32bit version. If you install 32-bit version and have 4GB or more RAM, you should install linux-generic-pae kernel from Synaptic Package Manager so that your system can make use of all of your RAM. Some users have also mentioned going to LinuxMint has solved their problems. Or if all elese fails, go back to Lucid (10.04) and wait for Natty Narwhal (11.04) to be released.

Hope this helps.
