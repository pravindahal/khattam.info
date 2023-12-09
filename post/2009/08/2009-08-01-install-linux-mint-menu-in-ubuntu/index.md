---
title: "[HOWTO]Install Linux Mint menu in Ubuntu"
date: "2009-08-01"
categories: 
  - "jaunty-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "icon"
  - "jaunty"
  - "jaunty-jackalope"
  - "linux"
  - "linux-mint"
  - "linuxmint"
  - "menu"
  - "ubuntu"
---

Here is how I installed Linux Mint Menu in Ubuntu 9.04 Jaunty Jackalope. I downloaded the following packages from the Linux Mint Repo which can be found [here](http://packages.linuxmint.com/ "LinuxMint Packages"):  
mintinstall  
mint-info  
mintsystem  
mintmenu  
These are the packages (current versions at the time of writing, I recommend you download them from the repository than from these links):  
http://packages.linuxmint.com/pool/main/m/mintinstall/mintinstall\_6.3.7\_all.deb  
http://packages.linuxmint.com/pool/main/m/mintsystem/mintsystem\_7.5.2\_all.deb  
http://packages.linuxmint.com/pool/main/m/mintmenu/mintmenu\_4.7.9\_all.deb

For my 64-bit version (amd64), the mint-info package is:  
http://packages.linuxmint.com/pool/romeo/m/mint-info-x64/mint-info-x64\_7.0.1\_all.deb

For 32-bit, it may be different. Try:  
http://packages.linuxmint.com/pool/main/m/mint-info-universal/mint-info-universal\_7.0.1\_all.deb

Now, install one by one in the following order:  
mintsystem  
mint-info  
mintinstall  
mintmenu

After the installation is done, right click on the panel and select Add to Panel. Then find mintmenu and add. To change the icon, right click on the menu and click on Preferences and then in the Button Icon, put in the full path to custom icon. You may want to put in /usr/share/icons/Human/22x22/places/start-here.png

Please share your results.
