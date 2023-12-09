---
title: "Ubuntu 9.04 Jaunty Jackalope repositories update fix"
date: "2009-07-09"
categories: 
  - "jaunty-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "jaunty"
  - "linux"
  - "repositories"
  - "ubuntu"
---

I am using Ubuntu 9.04 Jaunty Jackalope and recently encountered a problem updating the package sources or when reloading the repositories so was unable to add new repos via synaptic or apt-get. The console output was something like `Get: http://ftp.debian.org sid/main Sources Get: http://ftp.debian.org sid/contrib Sources Get: http://ftp.debian.org sid/non-free Sources Convert: acl...`

I searched for solutions and found it [here](http://forum.ubuntu-fr.org/viewtopic.php?id=319443).

It involves uninstalling two packages namely ia32-archive and ia32-apt-get via synaptic or apt-get.
