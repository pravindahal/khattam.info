---
title: "[SOLVED] Unable to get Exclusive Lock Problem While Launching Synaptic, /var/lib/dpkg/lock - open (11 Resource temporarily unavailable) Error"
date: "2010-01-28"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "varlibdpkgstatus"
  - "10-04"
  - "apt"
  - "apt-get"
  - "gksu"
  - "gnome-system-monitor"
  - "killall"
  - "linux"
  - "ltsp"
  - "ltsp-server"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "resource-temporarily-unavailable"
  - "subprocess"
  - "ubuntu"
  - "ubuntu-10-04"
  - "update"
  - "update-notifier"
---

I am using Ubuntu 10.04 Lucid Lynx Alpha and I encountered this while installing ltsp-server. The package being configured was ldm-server.

I was installing an application and Synaptic Package Manager just froze forever while configuring a package. I had to shut it down using sudo killall synaptic. Then, when I tried to launch t again, it would come up with "Unable to get Exclusive Lock" message. When I tried apt-get from Terminal, I got /var/lib/dpkg/lock - open (11 Resource temporarily unavailable).

I checked the processes by running "gksu gnome-system-monitor" from the run dialog, but could not find any packages related to apt or update. If you are facing the similar problem and if you find anything related to these, you should either stop the process from where it is running or kill them with gnome-system-monitor. I then killed update-notifier but that did not do it (that should not have done it anyways :)).

Then I just ran this in my terminal:

sudo rm /var/lib/dpkg/lock

i.e. I just removed /var/lib/dpkg/lock.  
This did it. I was able to open Synaptic Again.

But again I received "Sub Process Pre Removable Script Returned Error Exit Status X" problem, but solved it:  
http://www.khattam.info/2009/08/04/solved-subprocess-pre-removal-script-returned-error-exit-status-2-error/
