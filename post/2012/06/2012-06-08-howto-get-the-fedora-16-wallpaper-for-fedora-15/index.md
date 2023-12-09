---
title: "[HOWTO] Get the Fedora 16 wallpaper for Fedora 15"
date: "2012-06-08"
tags: 
  - "fedora"
  - "fedora-15"
  - "fedora-16"
  - "linux"
  - "wallpaper"
---

Fedora 16 Alpha is coming out soon and they have selected Fedora 16 wallpaper. Here is how I installed it in Fedora 15:

cd /tmp
wget http://kojipkgs.fedoraproject.org/packages/verne-backgrounds/15.91.0/1.fc16/noarch/verne-backgrounds-single-15.91.0-1.fc16.noarch.rpm
wget http://kojipkgs.fedoraproject.org/packages/verne-backgrounds/15.91.0/1.fc16/noarch/verne-backgrounds-15.91.0-1.fc16.noarch.rpm
rpm -i verne-backgrounds-single-15.91.0-1.fc16.noarch.rpm
rpm -i verne-backgrounds-15.91.0-1.fc16.noarch.rpm

Then, select the new wallpaper in background settings.
