---
title: "Jaunty Does Not Boot Up Under 25 Seconds? Try this."
date: "2009-05-02"
categories: 
  - "jaunty-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "boot-fast"
  - "jaunty"
  - "linux"
  - "ubuntu"
---

Ubuntu 9.04, Jaunty Jackalope, is expected to boot under 25 seconds from the grub to the desktop. However, you will probably not meet the expectations. Well, i didn't.

Try this. This will really improve your boot time to a considerable amount. Reboot and press escape to get to the booat loader (if you have other OS installed, you might well be presented with the Grub loader without pressing escape). Then press e. Now, you will see a line saying kernel. Highlight it and press e again. Now, type in --profile at the end of the line and press ENTER. Press b to boot.

This time, it will take too long to boot but the next time you boot, you should be really happy with the results.

This also works with older versions of Ubuntu.

But you may not get boot times up to 25 seconds or less if you have older hardware.
