---
title: "[HOWTO] Enable \"Mark All Upgrades\" in Synaptic on Linux Mint"
date: "2010-12-06"
categories: 
  - "debian-linux"
  - "isadora"
  - "julia"
  - "lmde"
tags: 
  - "helena"
  - "linux"
  - "linux-mint"
  - "mark-all-upgrades"
  - "synaptic"
---

If you are using Linux Mint Gnome or Linux Mint Debian Edition, you will notice that Ctrl+G or Mark All Upgrades is disabled. This has been done to prevent users from installing upgrades that have not been tested and verified to work by Linux Mint team. Read more in [this discussion](http://forums.linuxmint.com/viewtopic.php?f=47&t=46224).

However, if you can take care of your packages and the problems that may arise, you may want to enable the handy feature. It can be done by following the instructions below.

Open up the terminal and remove synaptic completely:

sudo apt-get purge synaptic

Then edit out the line in the following file or remove it completely. However, if you want to be able to enable it, it is recommended to just disable the line using a # in the beginning of the line.

/etc/linuxmint/adjustments/10-mintsystem-synaptic.overwrite

To edit it, you can open in any text editor as root. For example, to edit it using gedit, you may press Alt+F2 and enter the following:

gksu gedit /etc/linuxmint/adjustments/10-mintsystem-synaptic.overwrite

Make sure the line looks like the following by adding a # in the beginning of the line:

#/usr/lib/linuxmint/mintSystem/adjustments/synaptic.glade /usr/share/synaptic/glade/window\_main.glade

Save the file and exit. Then, install synaptic again:

sudo apt-get install synaptic

While removing Synaptic, note the packages being removed and install them back:

sudo apt-get install aptoncd apturl jockey-gtk mint-meta-gnome mint-meta-main mintupdate

That's it. Open up synaptic and you should be able to use "Mark All Upgrades" again.

If you wish to disable the mark all upgrades again, just remove synaptic and then remove the # from the same file and save it. Then, re-install synaptic again.

Hope it helps.
