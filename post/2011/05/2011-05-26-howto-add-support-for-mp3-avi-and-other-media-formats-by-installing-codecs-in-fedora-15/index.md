---
title: "[HOWTO] Add support for MP3, AVI and other media formats by installing codecs in Fedora 15"
date: "2011-05-26"
tags: 
  - "codecs"
  - "fedora"
  - "gnome-3"
  - "linux"
  - "totem"
---

I am running Fedora 15 Desktop and here is how I installed support for MP3, AVI and other media formats. I opened up the terminal and ran the following commands (enter root password when prompted):

su
yum localinstall --nogpgcheck http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-stable.noarch.rpm http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-stable.noarch.rpm
yum update

Now, close the terminal and open up media in Totem and it should prompt you to find and install appropriate codecs. The installation is to be done only once for a media format. Hope this helps.
