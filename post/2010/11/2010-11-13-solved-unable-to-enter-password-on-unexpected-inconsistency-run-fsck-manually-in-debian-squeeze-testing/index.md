---
title: "[SOLVED] Unable to enter password on \"UNEXPECTED INCONSISTENCY; RUN fsck MANUALLY\" in Debian Squeeze Testing"
date: "2010-11-13"
categories: 
  - "debian-linux"
tags: 
  - "fsck"
  - "linux"
---

My harddisk apparently had some problems and I got "check forced" and let fsck do its job during the startup. However, I got;

> /dev/sdXY: UNEXPECTED INCONSISTENCY; RUN fsck MANUALLY (i.e. without -a or -p options) fsck died with exit status 4 failed (code 4) File system check failed. A log is being saved in /var/log/fsck/checkfs if that location is writable. Please repair the filesystem manually ... failed! A maintenance shell will now be started. CONTROL-D will terminate and resume system boot. ... (warning) Give root password for maintainance (or CONTROL-D to continue):

However, when I tried to enter the password, I got "Login Incorrect" for each key I pressed. Even when I pressed CONTROL-D, I got the same. I am not sure if it is a result of me installing and enabling Plymouth recently, but I fixed it by booting up in recovery mode. In recovery mode, password was accepted. Then I got dropped into shell. I typed in fsck /dev/sdXY (where X is either A, B, C or D and Y is a number) and then typed "y" to offered fixes. Then, I could boot into the system.
