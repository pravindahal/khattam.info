---
title: "A better Torrent Client For Ubuntu 9.04 (Jaunty Jackalope)"
date: "2009-07-29"
categories: 
  - "jaunty-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "9-04"
  - "bittorrent-client"
  - "deluge"
  - "jaunty-jackalope"
  - "ktorrent"
  - "linux"
  - "torrent-client"
  - "ubuntu"
  - "ubuntu-9-04"
---

Transmission is the default torrent client with Ubuntu. However, I love ktorrent because of the various features it provides. As I use ubuntu and KDE based softwares require kdelibs to be installed, I usually go for alternatives and I found deluge to be a great alternative for ktorrent. It provides similar features as ktorrent.

It can be installed directly via Synaptic but for the latest version, just type in the following in the terminal window. The following instructions apply to Ubuntu 9.04 (Jaunty Jackalope). **1\. Add the deluge repository:** (Copy all the lines before step 2 at once, it is just a single line split because it was long. You may use triple click to select the whole line.) `sudo sh -c "echo 'deb http://ppa.launchpad.net/deluge-team/ppa/ubuntu jaunty main' >> /etc/apt/sources.list"`

**2\. Add the launchpad key:** a. Get launchpad key updater `wget "http://files.getdropbox.com/u/1113424/launchpad-update.tar.gz"` b. Extract it `tar -xf launchpad-update.tar.gz` c. Install it `sudo mv launchpad-update /usr/bin` d. Add keys `sudo launchpad-update`

**3\. Update your package list:** `sudo apt-get update`

**4\. Install** `sudo apt-get install deluge`

Now, to launch it, goto Applications > Internet > Deluge BitTorrent Client.
