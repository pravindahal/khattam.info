---
title: "[HOWTO] Install Flash Player in Fedora 15"
date: "2011-05-26"
tags: 
  - "adobe-flash-player"
  - "fedora"
  - "fedora-15"
  - "flash-player"
  - "linux"
---

I just installed Fedora 15 (Desktop i.e. standard) 64 bit and here is how I installed Adobe Flash Player 11b1 64bit version. I launched terminal and typed in the following commands.

su -c 'yum install wget'
cd /tmp
wget http://download.macromedia.com/pub/labs/flashplatformruntimes/flashplayer11/flashplayer11\_b2\_install\_lin\_64\_080811.tar.gz
tar xzvf flashplayer11\_b2\_install\_lin\_64\_080811.tar.gz
su -c 'cp libflashplayer.so /usr/lib64/mozilla/plugins/'
su -c 'cp -R usr/ /'

Then I restarted Firefox and Flash player is working. **Note:** This does not work for 32 bit version of Fedora. For 32-bit version, try this:

su
rpm -ivh http://linuxdownload.adobe.com/adobe-release/adobe-release-i386-1.0-1.noarch.rpm
rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-adobe-linux
yum update
yum install flash-plugin

Hope this helps.
