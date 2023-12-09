---
title: "[HOWTO] Update older Ubuntu iso images with zsync to get the latest version"
date: "2010-09-01"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "update-iso"
  - "zsync"
---

If you have downloaded an older daily build iso and want to update the iso with new daily build, you can use the zsync utility to get the latest version of daily build without having to download the whole of the new iso. Install zsync:

sudo apt-get install zsync

and then change the directory to where you have the older version of Ubuntu iso. For example, if you had downloaded maverick-desktop-i386.iso, go to the [same download location](http://cdimage.ubuntu.com/daily-live/current/) and find the file maverick-desktop-i386.iso.zsync, right click on it and copy link location. Now, in terminal, type the following to get the latest iso:

zsync http://cdimage.ubuntu.com/daily-live/current/maverick-desktop-i386.iso.zsync

Make sure you run it from the same directory where your old iso resides. When done, you will have the latest iso and a file maverick-desktop-i386.iso.zs-old which is the older version.

This can also be used to download less if the last download was partial and old. In fact, even if you have lucid iso, you can rename it and use zsync. It saves some bandwidth and time.
