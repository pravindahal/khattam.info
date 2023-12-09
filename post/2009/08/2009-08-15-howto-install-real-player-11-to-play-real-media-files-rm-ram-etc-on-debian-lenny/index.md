---
title: "[HOWTO] Install Real Player 11 to Play Real Media Files (rm, ram etc.) on Debian Lenny"
date: "2009-08-15"
categories: 
  - "debian-linux"
tags: 
  - "debian"
  - "lenny"
  - "linux"
  - "ram"
  - "real"
  - "real-media"
  - "real-player"
  - "realplayer"
  - "realplayer11"
  - "rm"
---

If you want to play real media files in Debian Lenny, you may not be able to play it. If that is the case or you want to install RealPlayer anyways, just follow the simple instructions.

Download deb from http://www.real.com/linux/. Make sure you click on DEB Package instead of the Download Realplayer button.

Now, open up the terminal and type in su followed by your root password. Now type in `apt-get update aup-get install lsb`

Now, change the directory to the one where you have downloaded the DEB file. In my case it is the Desktop, so I changed the directory to desktop by typing in `cd /home/YourUserName/Desktop`

Now, if you are on **32-bit version**, and the name of the DEB file is RealPlayer11GOLD.deb you should type in the following: `dpkg -i RealPlayer11GOLD.deb` and if you are on **64-bit version (amd64)**, you should type in `dpkg -i --force-arctecture RealPlayer11GOLD.deb` Now, run it from the Applications > Sound and Video > RealPlayer 11 and then configure it.
