---
title: "[HOWTO] Install VirtualBox 4.0 Final in Fedora"
date: "2010-12-23"
tags: 
  - "fedora"
  - "linux"
  - "virtualbox"
  - "virtualbox-4-0"
---

To install VirtualBox 4.0 in Fedora, first make sure you have removed old version of virtualbox and then open the terminal and type in su and enter password to login as root and type the following commands:

wget http://download.virtualbox.org/virtualbox/rpm/fedora/virtualbox.repo --output-document=/etc/repos.d/virtualbox.repo
yum update
yum install VirtualBox-4.0

VirtualBox will be installed and ready to use.

Hope this helps.
