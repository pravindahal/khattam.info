---
title: "[SOLVED] Volume always muted on startup"
date: "2010-06-16"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "10-10"
  - "9-10"
  - "audio"
  - "karmic-koala"
  - "linux"
  - "lucid-lynx"
  - "maverick-meerkat"
  - "mute"
  - "no-sound"
  - "sound"
  - "startup"
  - "unmute"
---

I'm using Ubuntu 10.10 Maverick Meerkat and I had been having a problem related to sound. Every time I started the computer, the volume was muted and I had to un-mute it as well as increase the volume. When I searched for a solution, it was brought to my attention that Ubuntu 9.10 Karmic Koala and 10.04 Lucid Lynx also had this problem. I solved it by simply removing the buggy package alsa-utils which was responsible for this. Removing also-utils also removes ubuntu-desktop meta-package, but it does not matter since it is just a meta-package. To those who do not want to remove alsa-utils or ubuntu-desktop, some people in the [Bug report](https://bugs.launchpad.net/ubuntu/+source/alsa-utils/+bug/352732) have said that removing the line

mute\_and\_zero\_levels "$TARGET\_CARD" || EXITSTATUS=1

from /etc/init.d/alsa-utils (to open, use gksu gedit /etc/init.d/alsa-utils) fixed the problem.
