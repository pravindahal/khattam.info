---
title: "[HOWTO] Install all the packages installed in one Ubuntu Installation to another"
date: "2010-11-12"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "aptitude"
  - "linux"
  - "packagebkp"
---

A recent [Web Upd8 article featured a tool called Meta Backup](http://www.webupd8.org/2010/11/meta-backup-makes-it-easy-to-export-all.html), which unfortunately fails to work as expected unless all the repositories are already configured and there are no orphan packages (not sure of the term, but I'm referring to those that are listed in Synaptic>Origin>Local) .

I created a simple script which can help achieve what Meta Backup wishes to achieve, which is to install the same set of packages in another computer running same version of Ubuntu. Please keep backup of your `/etc/apt` in both computers. I am not responsible for any harm done to you or your PC by using this script. Having said that, here it is:

[pkgbkp-0.04.tar.gz](https://mega.nz/file/M4B2kLTA#CblHYyBXQxpgb1eil4htbZ51fhauptKQK-iG-KnD_UE)

Extract it and run "packagebkp" from the terminal as root.
