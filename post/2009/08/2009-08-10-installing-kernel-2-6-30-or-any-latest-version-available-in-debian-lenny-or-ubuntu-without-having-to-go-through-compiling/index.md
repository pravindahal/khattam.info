---
title: "[HOW TO] Installing Kernel 2.6.30 (or any latest version available) in Debian Lenny or Ubuntu without having to go through Compiling"
date: "2009-08-10"
categories: 
  - "debian-linux"
  - "ubuntu-linux"
tags: 
  - "2-6-30"
  - "compiling"
  - "debian"
  - "hardy"
  - "intrepid"
  - "jaunty"
  - "kernel"
  - "latest"
  - "lenny"
  - "linux"
  - "ubuntu"
---

I have recently switched to Debian Lenny (from Ubuntu Jaunty Jackalope) and it is quite stable. However, I wanted to try the latest stable linux kernel (2.6.30 as of now) in this machine and see how it goes. However there are not much problems, I just wanted to install it. I went to [Debian Kernel Archive](http://kernel-archive.buildserver.net/ "Debian Kernel Archive") and downloaded the packages but it does not seem to work. So I headed over to the [Ubuntu Kernel Archive](http://kernel.ubuntu.com/~kernel-ppa/ "Ubuntu Kernel Archive") and the kernel there worked. This is how I did it.

I went to [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/) and downloaded: [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-headers-2.6.30-02063004-generic\_2.6.30-02063004\_amd64.deb](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-headers-2.6.30-02063004-generic_2.6.30-02063004_amd64.deb) [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-headers-2.6.30-02063004\_2.6.30-02063004\_all.deb](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-headers-2.6.30-02063004_2.6.30-02063004_all.deb) [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-image-2.6.30-02063004-generic\_2.6.30-02063004\_amd64.deb](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-image-2.6.30-02063004-generic_2.6.30-02063004_amd64.deb)

Yes, it is a 64-bit Lenny I have installed and hence the AMD64 versions. You may download: [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-headers-2.6.30-02063004-generic\_2.6.30-02063004\_i386.deb](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-headers-2.6.30-02063004-generic_2.6.30-02063004_i386.deb) [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-headers-2.6.30-02063004\_2.6.30-02063004\_all.deb](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-headers-2.6.30-02063004_2.6.30-02063004_all.deb) [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-image-2.6.30-02063004-generic\_2.6.30-02063004\_i386.deb](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.30.4/linux-image-2.6.30-02063004-generic_2.6.30-02063004_i386.deb) if your have 32-bit version of Lenny.

If you are on Debian Lenny or older version of Ubuntu, you will also need to download wireless-crda from [one Ubuntu Mirror](http://mirrors.kernel.org/ubuntu/pool/main/w/wireless-crda/) even if you don't use Wireless. Its just a 15KB download, don't worry. Choose version appropriate to your architecture. The latest version should do fine. As of now, the latest is 1.9 and here is the link to amd64 version: [http://mirrors.kernel.org/ubuntu/pool/main/w/wireless-crda/wireless-crda\_1.9\_amd64.deb](http://mirrors.kernel.org/ubuntu/pool/main/w/wireless-crda/wireless-crda_1.9_amd64.deb) and here it is for 32-bit: [http://mirrors.kernel.org/ubuntu/pool/main/w/wireless-crda/wireless-crda\_1.9\_i386.deb](http://mirrors.kernel.org/ubuntu/pool/main/w/wireless-crda/wireless-crda_1.9_i386.deb)

Now, if you have downloaded all of them, you can install it by double clicking on it (if you are in Ubutnu desktop)  or using dpkg -i filename.deb as root (if you are on Debian or Ubuntu) from the terminal for each of them. Now, if everything goes fine, you will see a new entry for the kernel next time when you boot your machine. You may even place them all inside one directory and execute dpkg -i \*.deb. If you want to install one-by one, you should first install wireless-crda, linux-header-all and then linux-header-amd64 (or i386) and then linux-image. I'm sure some other sequences work fine too, but if you are confused or don't want to waste your time figuring out which one goes first, you may want to follow the sequence I have stated here.

Hope this helps.

If you have reached this page when 2.6.30 is already outdated, you may want to share which version you have installed now.
