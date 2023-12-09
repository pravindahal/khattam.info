---
title: "[HOWTO] Install pastie in Debian Squeeze/Testing"
date: "2010-11-13"
categories: 
  - "debian-linux"
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "pastie"
---

Pastie is a clipboard manager for gnome with best feature set. It is available in Launchpad PPA for Ubuntu Lucid Lynx and Maverick Meerkat. However, it can be installed in Debian Squeeze/Testing from the same PPA.

To install, just open up Synaptic>Settings>Repositories>Third Party Software and click Add. Add the following line (yes Lucid, not Maverick):

deb http://ppa.launchpad.net/hel-sheep/pastie/ubuntu lucid main

When added, close the Repositories dialog and close Synaptic. Now, open up the terminal and execute the following commands:

sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys DE4CA452
sudo apt-get update
sudo apt-get install pastie python-gnome2

Note: If you are [not able to _sudo_](http://www.khattam.info/howto-enable-ubuntu-like-sudo-in-debian-squeeze-2010-11-14.html), use su followed by commands without "sudo" and it will work.

This should install pastie in your Debian. Have fun.
