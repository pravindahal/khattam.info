---
title: "[SOLVED] Could not start Ubuntu because root partition(/) full"
date: "2010-03-27"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "apt"
  - "blank-screen"
  - "linux"
  - "lucid"
  - "lucix-lynx"
  - "mandb"
  - "no-space-left-on-device"
  - "ubuntu"
  - "unable-to-login"
---

I upgraded my packages in my Ubuntu 10.04 Lucid Lynx Beta 1 installation and it required a restart. I did not realize that there was no space left on the root partition (I have two partitions, root / and /home). I restarted and was not able to login. I got a message saying something like

The configuration defaults for GNOME power manager have not been installed correctly. Please contact your computer administrator

in the Login window. I tried logging in again, but I again got blank screen and was logged back out. Nor did the message make any sense.

I pressed Ctrl+Alt+F1 and logged in there and then tried to upgrade the packages using

sudo apt-get update
sudo apt-get upgrade

There were upgrades available and installed them I saw mandb complaining about the lack of disk space. I then freed some space by deleting some files I had kept in the root directory and pressed Ctrl+Alt+Del to restart and it booted in without problems. If you face this problem and want to free some space, you can use

sudo apt-get clean

which will free the space used by package archives cache which are located at /var/cache/apt/archives and it should boot without problems.
