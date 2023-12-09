---
title: "[HOWTO] Install Linux Kernel 2.6.36 or 2.6.37 in Debian Squeeze Testing or Ubuntu or any Debian based distribution without compiling"
date: "2010-11-13"
categories: 
  - "debian-linux"
tags: 
  - "2-6-32"
  - "2-6-36"
  - "2-6-37"
  - "dpkg"
  - "gdebi"
  - "linux"
---

I have recently installed Debian Squeeze Testing and since I recently moved from Ubuntu 10.10 Maverick Meerkat (which has 2.6.35), I wanted to install it in my Debian Squeeze (which has 2.6.32). However, compiling kernel is time consuming and tiresome, I decided to use the [Ubuntu Kernel Mainline PPA](http://kernel.ubuntu.com/~kernel-ppa/mainline/) like I always do. I navigated to the latest 2.6.37 directory (which is v2.6.37-rc1-maverick as of today) and downloaded the following files: linux-headers-XXXXXX\_all.deb linux-headers-XXXXXX\_i386.deb (if you have 64bit, choose amd64 version) linux-image-XXXXXX\_i386.deb (if you have 64bit, choose amd64 version) Also, if you are not using Ubuntu, you may need to download [wireless crda package from maverick packages](http://packages.ubuntu.com/maverick/wireless-crda). After downloading, install in the following order (using dpkg or gdebi): wireless-crda linux-headers-XXXXXX\_all.deb linux-headers-XXXXXX\_i386.deb (if you have 64bit, choose amd64 version) linux-image-XXXXXX\_i386.deb (if you have 64bit, choose amd64 version)

Now, reboot and you should get booted into a new kernel. If you have problems booting into the new kernel, simply boot into the old kernel and remove it via package manager.
