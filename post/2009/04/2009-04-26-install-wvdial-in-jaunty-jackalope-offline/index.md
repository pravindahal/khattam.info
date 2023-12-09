---
title: "Install wvdial in Jaunty Jackalope offline"
date: "2009-04-26"
categories: 
  - "jaunty-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "gnome-ppp"
  - "jaunty"
  - "jaunty-jackalope"
  - "linux"
  - "wvdial"
---

If you used wvdial to connect to the internet, you will be disappointed with Jaunty as it does not have wvdial as a part of the default installation, which means you are unable to connect to the internet to download other required packages.You can accomplish the task using pppconfig from the terminal, but if it does not work or feel wvdial is what you need, then you may choose to install it by downloading the required files from a computer with internet access.

To find what files you need to install, open up Synaptic, search for gnome-ppp and mark it for installation. Press Apply and you should see the links of files that could not be downloaded. Copy the URLs and take them to a computer with internet access. After downloading, come back to your PC and then copy the downloaded files to /var/cache/apt/archives.

Now, launch Synaptic and search for wvdial. Mark gnome-ppp for installation and it should be installed.
