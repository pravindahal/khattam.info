---
title: "[HOWTO] Install the latest version of Shutter screenshot tool in Ubuntu"
date: "2010-11-11"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "shutter"
---

I am using Shutter screenshot tool as default screenshot tool. I installed it in my Ubuntu 10.10 Maverick Meerkat from the [Shutter Team official PPA](https://launchpad.net/~shutter/+archive/ppa). The latest available version in that PPA is 0.86~ppa4. The PPA has not been updated for quite some time now. I wanted some bugs to be fixed and when I saw bug pages, they had already been fixed in latest revision. So, I decided to install it.

To do so, I went through the following process. **Install Dependencies**

sudo apt-get install bzr libgtk2-unique-perl libimage-info-perl libimage-exiftool-perl

**Get latest Shutter**

bzr branch lp:shutter

**Install**

cd shutter
sudo cp bin/\* /usr/bin/
sudo cp -R share/\* /usr/share/

Now quit Shutter if you have it opened and launch it again.
