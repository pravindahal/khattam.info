---
title: "[HOWTO] Change Ubuntu 9.10 Karmic Koala to Linuxmint 8 Helena"
date: "2009-12-26"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "9-10"
  - "helena"
  - "karmic"
  - "karmic-koala"
  - "koala"
  - "linux"
  - "linux-mint"
  - "linuxmint"
  - "linuxmint-8"
  - "mint"
  - "mintconstructor"
  - "remaster"
  - "ubuntu-9-10"
  - "ubuntu-to-linuxmint"
---

As you know, Linuxmint is based on Ubuntu. So I thought, it might be possible to take Ubuntu as a base and turn it to Linuxmint with available Linuxmint software. Thats what I did.

I used Ubuntu Karmic Koala and turned it into Linuxmint Helena. You might use other Ubuntu base and turn it to respective Linuxmint distro, but you may need to follow different (yet similar) steps. Here is how I did it.

Please note that I am not trying to create Linuxmint Helena installation disk from Karmic Koala installation disk. What I am doing is turning a Karmic Koala installation to Linuxmint Helena Installation. However, after this is done, you may use mintconstructor to create Live+Installer CD/DVD for Linuxmint.

Disclaimer: I am not responsible for any kind of loss (time, data, your pet penguin.. whatever) you might face due to the instructions in this tutorial. Please proceed at your own risk.

**Installation of Ubuntu:** First of all, I installed Ubuntu 9.10 Karmic Koala. If you are reading this and have reached so far, I'll assume that you know how to install Ubuntu so I'm skipping the details. Just a standard Ubuntu Karmic Koala installation, nothing more nothing less. You may also use your existing Ubuntu Karmic Koala installation.

**Addition of repositories:**

Launch Synaptic and navigate to Settings>Repositories. In the other software tab, add the following lines one by one:

deb http://packages.linuxmint.com/ helena main upstream import backport
deb-src http://packages.linuxmint.com/ helena main upstream import backport #Added by software-properties
deb http://archive.ubuntu.com/ubuntu/ karmic main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu/ karmic-updates main restricted universe multiverse
deb http://security.ubuntu.com/ubuntu/ karmic-security main restricted universe multiverse
deb http://archive.canonical.com/ubuntu/ karmic partner
deb http://packages.medibuntu.org/ karmic free non-free

Now, Reload the package list by clicking on Reload.

When reloading is complete, search for package mint-meta-main and mark it for installation. This will select most mint software. Also, search for xsplash and mark it for removal. Now apply the changes and wait.

When the installation is complete, reboot. After you are back, you should get a mint-like system with softwares, theme and boot screen of Linuxmint.

**More:** You can add mint-menu to your panel by right clicking the panel>Add to Panel and select mintmenu. You can change the panel layout for it to look like Linuxmint. You may also create Linuxmint installation disk with the mintconstructor wizard (you will need to install mintconstructor first).

Hope this was helpful.
