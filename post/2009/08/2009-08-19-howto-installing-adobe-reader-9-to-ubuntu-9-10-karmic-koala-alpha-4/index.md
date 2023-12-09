---
title: "[HOWTO] Installing Adobe Reader 9 to Ubuntu 9.10 Karmic Koala Alpha 4"
date: "2009-08-19"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "9-10"
  - "adobe"
  - "adobe-reader"
  - "alpha-4"
  - "install-adobe-reader"
  - "karmic"
  - "karmic-koala"
  - "linux"
  - "ubuntu"
---

I tried to install Adobe Reader (acroread) in Ubuntu Karmic Koala Alpha 4 amd64 (64bit Version) that I use. I added [medibuntu repository](https://help.ubuntu.com/community/Medibuntu "Medibuntu") but package acroread was not available. Then, I downloaded deb from [http://get.adobe.com/reader/otherversions/](http://get.adobe.com/reader/otherversions/ "Adobe Flash Other Versions Download Plage") but 64-bit version (amd64) was not available. So I downloaded Linux x86 (.deb) version and then installed it with the following command via terminal: `sudo dpkg -i --force-architecture AdbeRdr9.1.2-1_i386linux_enu.deb`
