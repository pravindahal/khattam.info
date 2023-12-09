---
title: "[SOLVED] Error: unable to find the sources of your current Linux kernel. Specify KERN_DIR= and run Make again.  Stop."
date: "2010-11-26"
categories: 
  - "debian-linux"
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "headers"
  - "kernel"
  - "linux"
  - "modules"
  - "virtualbox"
---

I was trying to run Oracle Virtualbox in my Debian testing installation in which I have just installed Ubuntu Natty Kernel from Ubuntu repositories. I got an error followed by a dialog prompting me to run: /etc/init.d/vboxdrv setup as root.

However, it could not compile the kernel modules and I got the following error:

> Uninstalling modules from DKMS removing old DKMS module vboxhost version 3.2.10
> 
> \-------- Uninstall Beginning -------- Module: vboxhost Version: 3.2.10 Kernel: 2.6.32-5-686-bigmem (i686) -------------------------------------
> 
> Status: Before uninstall, this module version was ACTIVE on this kernel.
> 
> vboxdrv.ko: - Uninstallation - Deleting from: /lib/modules/2.6.32-5-686-bigmem/updates/dkms/ - Original module - No original module was found for this module on this kernel. - Use the dkms install command to reinstall any previous module version.
> 
> vboxnetflt.ko: - Uninstallation - Deleting from: /lib/modules/2.6.32-5-686-bigmem/updates/dkms/ - Original module - No original module was found for this module on this kernel. - Use the dkms install command to reinstall any previous module version.
> 
> vboxnetadp.ko: - Uninstallation - Deleting from: /lib/modules/2.6.32-5-686-bigmem/updates/dkms/ - Original module - No original module was found for this module on this kernel. - Use the dkms install command to reinstall any previous module version.
> 
> depmod......
> 
> DKMS: uninstall Completed.
> 
> \------------------------------ Deleting module version: 3.2.10 completely from the DKMS tree. ------------------------------ Done. Attempting to install using DKMS
> 
> Creating symlink /var/lib/dkms/vboxhost/3.2.10/source -> /usr/src/vboxhost-3.2.10
> 
> DKMS: add Completed. You can use the --kernelsourcedir option to tell DKMS where it's located, or you could install the linux-headers-2.6.37-6-generic-pae package. Failed to install using DKMS, attempting to install without Makefile:159: \*\*\* Error: unable to find the sources of your current Linux kernel. Specify KERN\_DIR= and run Make again. Stop.

I realized that I had just installed linux-image package only and not installed linux-headers while manually installing packages. This can be avoided by installing the corresponding headers. An easy way to do so is to run the following command:

sudo apt-get install dkms
sudo apt-get install linux-headers-\`uname -r|cut -d'-' -f3\`-\`uname -r|cut -d'-' -f4\`

If you are using the older kernel and not the latest version available in the repost\\itory, run the following:

sudo apt-get install dkms
sudo apt-get install linux-headers-\`uname -r\`

If you are on Debian, sudo may or may not be installed and it may or may not be configured for your user. Just use su to login as root and run the commands without sudo.

Hope this helps.
