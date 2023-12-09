---
title: "[HOWTO] Enable Ubuntu-like \"sudo\" in Debian Squeeze"
date: "2010-11-13"
categories: 
  - "debian-linux"
  - "ubuntu-linux"
tags: 
  - "gksu"
  - "gksudo"
  - "linux"
  - "sudo"
  - "sudoers"
---

In Ubuntu, when you need to run a command as root, you just have to run the command with a preceding "sudo" i.e.

sudo command-to-run

. However, in Debian (and many other Linux) it is may not be set as such by default. To set it as default and to allow the normal user to execute the command as root, just follow the following instructions:

**Install Sudo** To install sudo, just run the following commands:

su
apt-get install sudo gksu

**Add yourself to Sudoers list** First to open /etc/sudoers as root in terminal, run the follwing commands:

su
visudo

Now, scroll to the bottom of the file and add the following line:

username ALL=(ALL) ALL

where "username" is the username you use to login to your computer. Press Ctrl+O followed by ENTER to save /etc/sudoers and you are done.

Hope this helps.
