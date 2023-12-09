---
title: "[HOWTO] Remount /cdrom as Read-Write in a Live Unetbootin Setup"
date: "2010-12-17"
categories: 
  - "ubuntu-linux"
tags: 
  - "linux"
  - "unetbootin"
---

If you have used Unetbootin to setup a Live Ubuntu Environment, you will find that the partition containing the Unetbootin files will be mounted on /cdrom as read-only, which means, even if you launch nautilus with gksu or sudo, you will not be able to make changes to the file-system. There is however, an easy workaround which involves remounting the filesystem with a single command. Open up the terminal and type in the following:

sudo mount /cdrom  -o rw,remount

Now, you should be able to write into the filesystem.
