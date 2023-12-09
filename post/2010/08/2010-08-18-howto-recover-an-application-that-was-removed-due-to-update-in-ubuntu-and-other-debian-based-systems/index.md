---
title: "[HOWTO] Recover an application that was removed due to update in Ubuntu and other Debian based systems"
date: "2010-08-18"
categories: 
  - "debian-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "dpkg"
  - "filezilla"
  - "linux"
  - "synaptic"
---

Sometimes when you are using PPA repositories or mixing multiple repositories or using a Development version, you encounter a problem and some of your applications might be removed. I want to illustrate the problem with my current Ubuntu 10.10 Maverick Meerkat Alpha installation, which I use as the only OS in my computer. This is not recommended but since I have always managed to solve issues that come up due to development versions, I have mostly used development versions because I get to see the upcoming changes and report problems if anything that bothers me. With the latest repositories list update, I got into a problem with Filezilla, because I have been using Lucid getdeb repo with my system and Filezilla is in their repo as well as the official repo. When I marked for the latest updates in Synaptic Package Manager, I could see that filezilla, amongst others, was in the package to be removed which was because the package filezilla-common was to be upgraded and the filezilla that was installed, and had no update, had dependency issues. I upgraded the package filezilla-common anyways and lost filezilla. Ideally, since I am using a development version, I should have marked all the changes, and then reviewed the list of programs that are to be removed and unmark them or mark them for reinstallation which automatically unmarks the conflicting updates. Since packages like gdm, gnome-panel and some others which are required for the system to boot properly into the desktop were also marked for removal, I marked them for re-installation or unmarked them so that they remained in the system. But for experimenting, I did not mark it and it got removed. Now, when I try to install the package, I get the error:

> filezilla: Depends: filezilla-common (=3.3.2.1-1ubuntu1) but 3.3.3-1ubuntu1 is to be installed

and it cannot be marked for installation. Since I need filezilla, I need to get it back installed. For this, the easiest way is to remove the alternate repository and reload the software list. If that does not help, you could just wait for the next repository update and reload it and then install it. If you can’t wait or if that does not solve the problem, then you can follow the method I explained with 0ad here in my older blog post. I can also find the compatible deb file (download it from some other location and check for compatibility) and install it with gdebi (double click). If you can’t find it, just find the latest version (which may be found in the directory /var/cache/apt/archives or can be downloaded from http://packages.ubuntu.com) and then install with dpkg i.e.

sudo dpkg -i filezilla\_3.3.2.1-1ubuntu1\_amd64.deb

This will, however, leave broken packages and synaptic will not let you do any other installation/update without resolving it. But most of the time, you can run the particular program without problems. The next update might fix the problem and you can just reinstall the broken package. But in case if it does not or if you don’t want to wait, you can downgrade to the older version of the conflicting package that you upgraded which caused your program to be removed. You can find the deb online or in /var/cache/apt/archives and install it using dpkg. In my case, it is the older version of filezilla-common that I need. So, all I do is run the following command to install the older version which will replace the newer version:

sudo dpkg -i /var/cache/apt/archives/filezilla-common\_3.3.3-1~getdeb2\_all.deb

and then to reconfigure the package filezilla, I also installed the older version of filezilla:

sudo dpkg -i /var/cache/apt/archives/filezilla\_3.3.3-1~getdeb2\_amd64.deb

Hope this helps resolving and recovering your lost programs.
