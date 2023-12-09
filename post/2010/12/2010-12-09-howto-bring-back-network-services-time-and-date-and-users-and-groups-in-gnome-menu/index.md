---
title: "[HOWTO] Bring back \"Network\", \"Services\", \"Time and Date\" and \"Users and Groups\" in Gnome Menu"
date: "2010-12-09"
categories: 
  - "debian-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "linux-mint"
  - "menu"
  - "network"
  - "services"
  - "time-and-date"
  - "users-and-groups"
---

If you have installed your system via netinstall or by selecting packages one by one, or if you somehow removed some gnome packages, you may be missing some menu items. I noticed that I did not have some entries in System>Administration menu, namely, "Network", "Services", "Time and Date" and "Users and Groups". I tried to search for them in Synaptic and Apt-file but failed to locate the exact package. So, I did some hit and trial and found the package was "gnome-system-tools". I just installed it via synaptic and the menu entries were back.
