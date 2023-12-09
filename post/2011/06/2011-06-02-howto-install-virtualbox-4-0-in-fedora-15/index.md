---
title: "[HOWTO] Install VirtualBox 4.0 in Fedora 15"
date: "2011-06-02"
tags: 
  - "fedora"
  - "linux"
  - "virtualbox"
  - "yum"
---

Here is how you can install VirtualBox in Fedora 15. Open up the terminal and type in the following commands (make sure you have [enabled sudo](http://www.khattam.info/howto-enable-sudo-in-fedora-15-2011-05-31.html) for your user):

wget -q http://download.virtualbox.org/virtualbox/debian/oracle\_vbox.asc -O- | rpm --import -
sudo wget http://download.virtualbox.org/virtualbox/rpm/fedora/virtualbox.repo --output-document=/etc/yum.repos.d/virtualbox.repo
sudo yum install VirtualBox-4.0 dkms

Hope this helps.
