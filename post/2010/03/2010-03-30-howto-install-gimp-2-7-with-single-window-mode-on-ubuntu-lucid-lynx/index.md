---
title: "[HOWTO] Install GIMP 2.7 (with Single Window Mode) on Ubuntu Lucid Lynx"
date: "2010-03-30"
categories: 
  - "jaunty-ubuntu-linux-linux"
  - "karmic-ubuntu-linux-linux"
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "gimp"
  - "gimp-2-7"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "single-window-mode"
  - "ubuntu"
---

GIMP 2.7.1 added Single Window Mode and GIMP 2.7.x can now be installed via PPA. It is available [here](https://launchpad.net/~matthaeus123/+archive/mrw-gimp-svn) for Jaunty, Karmic and Lucid. I have Ubuntu 10.04 Lucid Lynx installed and I installed GIMP 2.7.3 unstable. Here is how you can do it, but if you use it for production, you might want to wait for final stable release.

Launch Synaptic Package Manager and click Settings>Repositories>Other Software and then Add

ppa:matthaeus123/mrw-gimp-svn

. Reload the software list and mark for upgrades. That will install GIMP 2.7 and you can enable the Single Window Mode by navigating to Window>Single Window Mode.
