---
title: "[HOWTO] Update vuze (azureus) to latest version 4.5 in Ubuntu 10.10 Maverick Meerkat"
date: "2010-09-09"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "azureus"
  - "bit-torrent"
  - "bittorrent"
  - "java"
  - "linux"
  - "torrent"
  - "vuze"
---

I installed Vuze bit-torrent client and it seems really awesome. It has been written in Java but it is pretty fast and awesome. It has search and many helpful plugins. It has various types of options and configurations and it will sure take me some time to figure out. I installed it from Synaptic Package Manager and got the version 4.3.0.6 (Ubuntu Software Center will do the same). I went to the website and saw that 4.5.0.4 was available already. I downloaded the linux installer (Vuze\_Installer.tar.bz2) and unpacked it. I got a directory named "vuze" which contained the files. Then, I just launched terminal and changed the directory to "vuze", the one that I just extracted. Then, I just had to copy the files to where they belong. Remember, you must have the version from the package manager installed. Then, I just backed up the original vuze files and then copied the new files over.

sudo mv /usr/share/java/Azureus2.jar /usr/share/java/Azureus2.jar.bak
sudo cp Azureus2.jar /usr/share/java/Azureus2.jar
sudo mv /usr/share/java/swt.jar /usr/share/java/swt.jar.bak
sudo cp swt.jar /usr/share/java/swt.new.jar
sudo ln -s /usr/share/java/swt.new.jar /usr/share/java/swt.jar

Now, restart vuze to check if everything works well. If it does, great, congratulations. Check the version and check if it was successfully updated.

However, if it does not run well or does not run at all, you can always get back the original installation. One way to do that is "Mark for Reinstallation" from Synaptic Package Manager (or remove and install again from Ubuntu Software Center), the other way is to undo whatever you have done via the command, which is pretty easy to figure out.

Hope this helps.
