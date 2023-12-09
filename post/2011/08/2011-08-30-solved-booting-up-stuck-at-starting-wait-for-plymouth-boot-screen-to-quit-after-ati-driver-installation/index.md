---
title: "[SOLVED] Booting up stuck at \"Starting Wait for Plymouth Boot Screen to Quit\" after ATI Driver Installation"
date: "2011-08-30"
tags: 
  - "ati"
  - "ati-radeon-hd"
  - "ati-radeon-hd-6470m"
  - "catalyst"
  - "fedora"
  - "hp-pavilion"
  - "intel"
  - "linux"
  - "switchable-graphics"
---

I installed Fedora 15 on HP Pavilion G4 1009tx Notebook recently. It has Intel Onboard Graphics and ATI Radeon HD 6470M Graphics 1024MB GDDR3, with switching option in Windows. However, it was disappointing to see that Gnome-Shell does not load on it while used to run fine on my old Desktop with onboard Intel Graphics. I tried to install ATI Properiatary drivers from RPM Fusion repos. However, after reboot, the booting process halted after showing the following:

Starting SYSV: Enable monthly update of Smolt...

Started SYSV: Enable monthly update of Smolt.

Starting SYSV: Grant or revoke access to X for the ATI External Events Daemon...

Started SYSV: Grant or revoke access to X for the ATI External Events Daemon.

Starting SYSV: Late init script for live image....

Starting /etc/rc.local Compatibility...

Started SYSV: Late init script for live image..

Started /etc/rc.local Compatibility.

Starting Wait for Plymouth Boot Screen to Quit...

I discovered that I could still navigate to virtual terminals by pressing Ctrl+Alt+F2, F3 and so on. So, I decided to remove the catalyst drivers so that I could boot into my PC again. I logged in as root and ran the following to show the latest installed packages:

cat /var/www/yum.log

The most recently installed were the packages related to ATI drivers:

Aug 31 02:29:01 Installed: xorg-x11-drv-catalyst-libs-11.7-1.fc15.x86\_64
Aug 31 02:29:08 Installed: xorg-x11-drv-catalyst-11.7-1.fc15.x86\_64
Aug 31 02:29:08 Installed: akmod-catalyst-11.7-1.fc15.x86\_64
Aug 31 02:29:10 Installed: xorg-x11-drv-catalyst-libs-11.7-1.fc15.i686

So, to remove I typed the following:

yum remove xorg-x11-drv-catalyst

Then, I rebooted the PC with the reboot command. Now, the Laptop boots successfully but still has no 3D graphics. I guess I will have to stay with the boring Gnome 3 fallback interface unless I figure something else out. :(
