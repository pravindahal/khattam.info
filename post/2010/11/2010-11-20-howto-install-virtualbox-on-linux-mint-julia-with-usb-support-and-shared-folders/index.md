---
title: "[HOWTO] Install Virtualbox on Linux Mint Julia with USB Support and Shared Folders"
date: "2010-11-20"
categories: 
  - "julia"
tags: 
  - "linux"
  - "linux-mint"
  - "virtualbox"
  - "virtualbox-nonfree"
  - "virtualbox-ose"
  - "windows"
---

There are many Virtualization solutions that run on Linux and of course Linux Mint. Oracle Virtualbox is a virtualization software available for Linux, Solaris, Windows and Mac, . It is available from the Linux Mint Julia Repositories and can be installed directly via Software Manager. However, if you install the open source version i.e. virtualbox-ose package, you will not be able to connect your USB devices and share folders between Guest and Host machines. File sharing can be set up in other ways, but if you wish to use one of your USB devices which has no Linux drivers, you may need to install Windows inside Virtualbox and connect your devices so that you can install drivers inside. In that case, you will need to install closed source edition of Virtualbox i.e. virtualbox-nonfree.

After you install virtualbox-nonfree, you will be able to run and install Guest operating systems inside. However, this version may nag you about updates being available. Linux Mint repositories will be updated regularly and you will be able to install latest version so you can disable the updates checking in Virtualbox>File>Preferences>Update.
