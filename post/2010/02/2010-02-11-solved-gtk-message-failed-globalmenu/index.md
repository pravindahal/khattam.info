---
title: "[SOLVED] Gtk-Message: Failed to load module \"gnomenu-panel\""
date: "2010-02-11"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "lucid-ubuntu-linux-linux"
  - "mac"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "gnomenu"
  - "gtk"
  - "karmic"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "mac-os"
  - "mac-os-x"
  - "murrine"
  - "terminal"
  - "ubuntu"
  - "ubuntu-10-04"
---

I am using globalmenu 0.7.9 (Mac OS X like Global menu for Gnome) from the [globalmenu-team PPA](https://launchpad.net/~globalmenu-team/+archive/ppa) (Karmic as Lucid is not available now) in my Ubuntu 10.04 Lucid Lynx. I get the following error on terminal when I try to launch any gtk applications from the terminal:

Gtk-Message: Failed to load module "gnomenu-panel": libgnomenu-panel.so: cannot open shared object file: No such file or directory
Gtk-Message: Failed to load module "globalmenu-gnome": libglobalmenu-gnome.so: cannot open shared object file: No such file or directory

  
However, the gnomemenu-panel works fine, I wanted these messages to not appear.  
I opened up /usr/lib/gtk-2.0/modules and found that the plugin had different files than listed in the error message. To fix the problem, I just created symbolic links to the existing files. This is how I did it from the terminal:

cd /usr/lib/gtk-2.0/modules
sudo ln -s libglobalmenu-gnome-panel.so libglobalmenu-gnome.so
sudo ln -s libglobalmenu-gnome-panel.so libgnomenu-panel.so

and the messages are gone.

Hope this helps.
