---
title: "[HOWTO] Install latest Intel DRM Kernel to avoid crashes on boards with Intel HD Graphics"
date: "2010-08-14"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "2-6-35"
  - "core-i3"
  - "crash"
  - "intel-hd"
  - "kernel"
  - "linux"
---

My friend has a laptop with Intel Core i3 and onboard Intel HD graphics. His Ubuntu used to crash very often. He is using latest Ubuntu 10.04 Lucid Lynx. He then upgraded to latest kernel 2.6.35-997 from drm-intel-next from drm-intel-next PPA which has stopped the crashing. However, the kernel is development kernel and you should use it with caution. If it fails to boot or causes problems, you can always hold on shift key during boot and then boot into the older kernel and remove it from the package manager. Having said that, here is how to install the latest kernel in Ubuntu from the drm-intel-next PPA. Goto [drm-intel-next PPA](http://kernel.ubuntu.com/~kernel-ppa/mainline/drm-intel-next/2010-08-04-maverick/) and then download the following files: linux-headers-X-all.deb linux-headers-X.deb linux-image-X.deb Here, X is the version which you can use whatever is available and refers to your Ubuntu architecture. In the PPA, 32-bit (i386) and 64-bit (amd64) are available. If you don’t know the architecture of your installation, you can easily check by typing the command

uname -m

in the terminal. If it says x86\_64, you should go for amd64 and if it says iX86 (i686 for example), go for i386. After the download, install in the above order and reboot and it should boot into your newly installed kernel.

Hope this helps.
