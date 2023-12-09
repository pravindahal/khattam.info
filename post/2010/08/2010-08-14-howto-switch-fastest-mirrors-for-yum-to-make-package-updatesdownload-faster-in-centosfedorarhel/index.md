---
title: "[HOWTO] Switch fastest mirrors for yum to make package updates/download faster in CentOS/Fedora/RHEL"
date: "2010-08-14"
categories: 
  - "centos-rhel"
tags: 
  - "change-fastest-mirrors"
  - "force-mirror-updates"
  - "linux"
  - "yum"
  - "yum-fastestmirrors"
---

I just installed CentOS 5.5 in one of my servers and it seems great. I ran yum for the first time and it selected a mirror for me which was really very slow, almost useless. So, package updates and installation were taking a lot of time. I decided to switch to a different repo but didn't have an idea which, so I decided to let the same fastest-mirrors plugin decide the mirrors. To force yum-fastestmirror plugin to check for fastest mirrors, you must delete the file /var/cache/yum/timedhosts.txt by running the following command as root:

rm /var/cache/yum/timedhosts.txt

Then, running yum will check for fastest mirror next time it is run. It should pick up a better mirror, but in my case, it just picked the same mirror over and over. So, I decided to block it altogether so that yum-fastestmirror is forced to choose another one.To do that, I opened the file /etc/yum/pluginconf.d/fastestmirror.conf as root and uncommented the line (removed the “#”) with “exclude” and added the culprit mirror “mirror.eshk.hk” to the exclude list so that the line looked like the following:

exclude=mirror.eshk.hk

If yum-fastestmirror keeps on giving selecting slow mirrors, you can add additional mirrors to the exclude list (separate mirror names with commas) and remove /var/cache/yum/timedhosts.txt again and repeat it again and again till you are satisfied with the speeds.
