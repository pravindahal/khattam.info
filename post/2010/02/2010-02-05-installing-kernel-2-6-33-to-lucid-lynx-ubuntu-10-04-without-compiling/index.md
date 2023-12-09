---
title: "[HOWTO] Installing Kernel 2.6.33 on Lucid Lynx (Ubuntu 10.04) without compiling"
date: "2010-02-05"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "2-6-33"
  - "ati"
  - "install"
  - "kernel"
  - "linux"
  - "lts"
  - "lucid"
  - "lucid-2-6-33"
  - "lucid-lynx"
  - "lynx"
  - "nouveau"
  - "nvidia"
  - "ubuntu"
  - "ubuntu-2-6-33"
  - "update"
---

I'm using Ubuntu 10.04 Lucid Lynx Alpha and I decided to check out the latest RC kernel from the Kernel PPA. This is how I installed it on my i386 (32-bit) installation of Ubuntu.  

UPDATE: The final 2.6.33 is out, it can be downloaded from [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.33/](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.33/)

I downloaded the following files from: [http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.33-rc6/](http://kernel.ubuntu.com/~kernel-ppa/mainline/v2.6.33-rc6/)  
linux-headers-2.6.33-020633rc6-generic\_2.6.33-020633rc6\_i386.deb  
linux-headers-2.6.33-020633rc6\_2.6.33-020633rc6\_all.deb  
linux-image-2.6.33-020633rc6-generic\_2.6.33-020633rc6\_i386.deb

Then, I installed them one by one (double click and click install) in the following order:  
linux-headers-2.6.33-020633rc6\_2.6.33-020633rc6\_all.deb  
linux-headers-2.6.33-020633rc6-generic\_2.6.33-020633rc6\_i386.deb  
linux-image-2.6.33-020633rc6-generic\_2.6.33-020633rc6\_i386.deb

If you are using amd64 (64-bit) installation, you should download the files with amd64 instead of i386. The latest release till date is v2.6.33-rc6. A later version may be available till you read this. First, check the versions at [http://kernel.ubuntu.com/~kernel-ppa/mainline/](http://kernel.ubuntu.com/~kernel-ppa/mainline/) and choose the latest one.

Although the new Kernel promises better support for graphics (nouveau), I did not find any improvements as such with my onboard Intel GMA 3100 Graphics (actually I didn't do any benchmarks, I just ran Assaultcube and it looks and feels the same coz it ran pretty well already :)). I think Nvidia and ATI users will feel the difference though. Also, the boot up has slowed down and usable desktop shows up very late. I also see a lot of disk activity immediately after the boot up. I don't know what is causing this. I couldn't find any errors as such in kernel log. I'll keep this one for now and see how it goes. I will update when the newer build is out.

Please share your 2.6.33 experience.
