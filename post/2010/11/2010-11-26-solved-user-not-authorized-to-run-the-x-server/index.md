---
title: "[SOLVED] User not authorized to run the X server"
date: "2010-11-26"
categories: 
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "startx"
  - "x"
  - "x-org"
  - "x11"
  - "xorg"
  - "xserver"
---

My friend recently installed Ubuntu 11.04 Natty Narwhal. He is not able to boot into the Desktop Environment. As he was trying to fix things up, he got this error while running startx:

> User not authorized to run the X server , aborted

With a little bit of searching, we were able to find a solution in [Ubuntu Forums](http://ubuntuforums.org/showthread.php?t=193079).

The trick is to reconfigure x11-common for "Anyone". This can be done by running the following command in the terminal:

sudo dpkg-reconfigure x11-common

Then, select the option "Anyone" and then run startx.
