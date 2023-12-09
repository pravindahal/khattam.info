---
title: "[HOWTO] Make Docky 3-D Style in Ubuntu"
date: "2009-12-30"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "3d"
  - "docky"
  - "gconf-editor"
  - "gnome-do"
  - "karmic"
  - "karmic-koala"
  - "koala"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "ubuntu"
---

Docky is a great dock for Linux and is based on Gnome-do.  

![](images/Screenshot-1.png)

**Installation**  
If you haven't already installed it, you can add the following repositories to your Ubuntu 9.10 Karmic Koala or Lucid Lynx: "ppa:docky-core/ppa" in Synaptic Package Manager>Settings>Repositories then reload. Then you can simply install it from Synaptic.

Now, launch it (Alt+F2>docky or Accessories>Docky) and then right click settings to configure it. After you are done configuring it, you can simply add applications to it by dragging them from the menu and dropping it on the docky.

After you are done configuring it, you may also want the 3-D look it offers. To get the 3D look, you will need to launch gconf-editor (Alt+F2>gconf-editor) and then navigate to /apps/docky-2/Docky/Interface/DockPreferences/DockX where X=1, 2, 3... the number of your Dock. On the right hand pane, look for Position and make sure it is set to Bottom (this is the default). Now, check the checkbox next to ThreeDimensional. To view the changes, you will need to quit docky and start it again.  
Hope this helped.
