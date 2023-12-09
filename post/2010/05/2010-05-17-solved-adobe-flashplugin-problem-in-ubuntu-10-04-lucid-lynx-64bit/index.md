---
title: "[SOLVED] Adobe FlashPlugin Problem in Ubuntu 10.04 Lucid Lynx 64bit"
date: "2010-05-17"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "firefox"
  - "firefox-3-5"
  - "flash"
  - "flash-plugin"
  - "flashplugin"
  - "karmic"
  - "karmic-koala"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "mozilla"
  - "ubuntu"
  - "web"
  - "youtube"
---

I had posted about flash plugin controls not working in Ubuntu 9.10 Karmic Koala 64 bit [here](http://www.khattam.info/2009/08/18/solved-flashplugin-controls-not-working-in-ubuntu-9-10-karmic-koala-alpha-4/). I had moved to Ubuntu 32 bit for quite sometime and recently made a move back to Ubuntu 64 bit. I found the same problem with flash plugin controls in Ubuntu 64 bit. Sometimes it works, and sometimes it doesn't. I haven't found any specific patterns to when it does and when it doesn't. If someone has, please do share.

In my previous post regarding the issue, I had suggested the installation of Adobe flash player 64 bit version from [Adobe Labs website](http://labs.adobe.com/downloads/flashplayer10.html). The solution worked fine for me and it seems for most of the others, but the plugin was experimental and when someone needed to update, it was not available via repositories. It has been provided in a launchpad ppa repository currently which can be added by adding **ppa:sevenmachines/ppa** to Repositories in Synaptic, but it seems it is not updated as of now and the latest version available in the ppa is 10.0.45.2 while Adobe has already released version 10.1rc4. But since the latest version is not recognized by youtube, I think we should stay with the version in the repository.

Simply open up synaptic and navigate to Settings>Repositories>Other Software and click on Add. In the apt-line, enter ppa:sevenmachines/flash and close it. Then Click on the Reload button. Now, search for flashplugin64-installer, mark it for installation and click on apply.

When done, restart firefox and flash should run fine.

Please share your flash player 10 experience in Linux.
