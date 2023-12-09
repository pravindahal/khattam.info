---
title: "[SOLVED] VirtualBox, LTSP, \"SMBus base address uninitialized - upgrade BIOS or use force_addr=0xaddr\""
date: "2010-01-29"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "bios"
  - "freeze"
  - "frozen"
  - "linux"
  - "ltsp"
  - "lucid"
  - "lucid-lynx"
  - "processor"
  - "virtualbox"
---

As I have mentioned in the [previous post](http://www.khattam.info/2010/01/30/solved-ltsp-error-ltsp-client-installation-ended-abnormally/), I was experimenting with LTSP on my Ubuntu 10.04 Lucid Lynx Alpha installation. I set up ltsp client and then created a diskless VirtualBox Virtual Machine with Network Boot as First Boot Option. I tried to boot it and it an error came up. It said:

SMBus base address uninitialized - upgrade BIOS or use force\_addr=0xaddr

and just froze there.  
Since I have Core 2 Duo, I set up two processors in the System>Processor. I just set it back to one processor and despite of the error, the LTSP server booted successfully.
