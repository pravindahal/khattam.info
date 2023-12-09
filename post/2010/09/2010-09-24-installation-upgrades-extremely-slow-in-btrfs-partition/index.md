---
title: "[SOLVED] Installation/Upgrades extremely slow in BTRFS partition"
date: "2010-09-24"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "2-6-36"
  - "btrfs"
  - "linux"
  - "slow-installation"
  - "slow-upgrade"
---

UPDATE: I installed a modified version of dpkg which makes it pretty much faster. Brian Rogers posted the [patched dpkg ppa](https://launchpad.net/~brian-rogers/+archive/btrfs) in the [bug page](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/601299). The patched dpkg can be installed by executing the following commands:

sudo apt-add-repository ppa:brian-rogers/btrfs
sudo apt-get update
sudo apt-get upgrade

**Older Post follows for historical reasons:** I am using Ubuntu 10.10 Maverick Meerkat Beta and was experiencing extremely slow installation/upgrades. I was using Maverick Alpha 2 which I replaced with Alpha 3 with clean install and changed the root partition to BTRFS. Copying was normal but for some reason, package installation and upgrades took ages.

Later, it was also declared that BTRFS was not making into Maverick final and we would have to wait till the release of Ubuntu 11.04, Natty Narwhal. I read in a bug report that a patch had been issued but this has not made into the latest 2.6.35-22. Hopefully, this will be included when the final version of Maverick comes out.

Meanwhile, I decided to upgrade to 2.6.36 kernel from [Kernel Mainline PPA](http://kernel.ubuntu.com/~kernel-ppa/mainline/). The latest version as of today is 2.6.36-020636rc5 (2.6.36-rc5). I downloaded the following files and installed them in the same order: linux-headers-2.6.36-020636rc5\_2.6.36-020636rc5.201009211328\_all.deb linux-headers-2.6.36-020636rc5-generic\_2.6.36-020636rc5.201009211328\_**i386**.deb linux-image-2.6.36-020636rc5-generic\_2.6.36-020636rc5.201009211328\_**i386**.deb

If you have a 64-bit installation, you should download the following instead: linux-headers-2.6.36-020636rc5\_2.6.36-020636rc5.201009211328\_all.deb linux-headers-2.6.36-020636rc5-generic\_2.6.36-020636rc5.201009211328\_**amd64**.deb linux-image-2.6.36-020636rc5-generic\_2.6.36-020636rc5.201009211328\_**amd64**.deb

I rebooted and tried installing some packages. The bug still remains. It is definitely not fast as I'd expect it to be. It is still very slow compared to previous experiences with ext3/ext4. I will wait for the new version of 2.6.36 to appear on Kernel Mainline PPA.
