---
title: "[HOWTO] Allow normal users to shutdown without entering password"
date: "2010-11-19"
categories: 
  - "debian-linux"
tags: 
  - "halt"
  - "linux"
  - "shutdown"
---

I am using Debian Squeeze Testing and I wanted to allow myself to shutdown without entering root password. To do so, I just executed the following as root:

chmod +s /sbin/reboot
chmod +s /sbin/halt

Note that this will allow any user to shutdown.
