---
title: "[HOWTO] Install Linux Kernel 3.0 in Ubuntu 11.04 Natty Narwhal"
date: "2011-06-03"
categories: 
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "kernel"
  - "kernel-3-0"
  - "linux"
  - "oneiric-ocelot"
---

Linux Kernel 3.0 RC 1 was recently released. Although it does not have real changes to anything, but is just a renaming of 2.6.40, however, you may want to install it for testing and using it if it works good for you in your Ubuntu Natty installation. It has bug fixes and additional drivers so it may solve problems. However, it may also introduce new problems, so be careful not to remove the other kernel (2.6.38) after installing it. This tutorial also contains instructions to remove it safely, so read along. Ubuntu 11.10 Oneiric Ocelot will be released with kernel 3.0.

As of writing this, only amd64 (64 bit version) of the kernel is available in [Kernel PPA](http://kernel.ubuntu.com/~kernel-ppa/mainline/v3.0.1-oneiric/), so if you are using 32-bit, it will not work for you. However, if you find i386 builds in the kernel ppa, you can install it. (**UPDATE:** Now both 32-bit and 64-bit versions are available)

First of all, download the debs from [Kernel PPA](http://kernel.ubuntu.com/~kernel-ppa/mainline/v3.0.1-oneiric/). Then install in this order: linux-headers linux-headers-generic linux-image

Once installation is done, reboot and Ubuntu should boot into 3.0 by default. If everything works right, you may want to keep it, however, if it does not, don't worry, just reboot and select one of the previous versions and boot into it. Then open up synaptic, search for linux-headers-3 and linux-image-3 and remove the 3.0 versions.

If you are reading this after other versions are released, you may want to check out [kernel ppa](http://kernel.ubuntu.com/~kernel-ppa/mainline/).
