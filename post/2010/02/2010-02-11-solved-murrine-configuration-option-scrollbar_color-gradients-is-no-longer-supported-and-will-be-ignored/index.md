---
title: "[SOLVED] 'Murrine configuration option \"scrollbar_color\", \"gradients\" is no longer supported and will be ignored.'"
date: "2010-02-11"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "balazan"
  - "configuration"
  - "gtk"
  - "gtkrc"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "murrine"
  - "terminal"
  - "ubuntu"
  - "ubuntu-10-04"
---

I am using balazan theme in Ubuntu 10.04 Lucid Lynx Alpha 4 from [breathe ppa](https://launchpad.net/~breathe-dev/+archive/ppa) for Karmic Koala since Lucid PPA was not available when I started using Lucid. I saw this message when I launched gedit from terminal (gnome-terminal):

/usr/share/themes/balanzan/gtk-2.0/gtkrc:89: Murrine configuration option "scrollbar\_color" is no longer supported and will be ignored.
/usr/share/themes/balanzan/gtk-2.0/gtkrc:93: Murrine configuration option "gradients" is no longer supported and will be ignored.

  
Seems like the theme I'm using has some depreciated configuration options after Murrine update. I opened the /usr/share/themes/balanzan/gtk-2.0/gtkrc file (as root) using the following command from Alt+F2

gksu gedit /usr/share/themes/balanzan/gtk-2.0/gtkrc

and then removed the lines in question (89 and 93 in my case, those that contain depreciated options) and saved it. The messages are gone.  
Hope this helps.
