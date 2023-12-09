---
title: "The Best Ubuntu Dock and How to install it in Ubuntu Intrepid amd64"
date: "2009-04-15"
categories: 
  - "ibex"
  - "ubuntu-linux"
tags: 
  - "64bit"
  - "dock"
  - "gnome"
  - "gnome-do"
  - "intrepid-ibex"
  - "linux"
  - "ubuntu"
---

I recently encountered a [Youtube video](http://www.youtube.com/watch?v=j5CWtf9ASRo&feature=related "gnome do + docky = awesome") which featured Gnome Do with Docky. Then I dumped the Cairo Dock I was using and replaced it with Gnome Do. I have also tried kiba-dock which is quite buggy (it is in developement). I also tried the Avant Window Navigator but found it was not so good to my liking.

The Gnome Do features the Advanced indicators which mimics the OS X dock and it is totally awesome.

To install it on your machine, you can follow the instructions in the [Gnome Do Wiki](http://do.davebsd.com/wiki/index.php?title=Installing_Do "Installing Do"). If you have 64-bit Ubuntu Intrepid Ibex, you will need to use [the workaround](https://launchpad.net/~do-core/+archive/ppa "Workaround for Ubuntu Intrepid 64bit Users"). This involves downloading the deb of 0.8 as the repo only provides the older version and shows an error. Plugins, however, can be downloaded via Synaptic (or package manager of your choice).

To enable the dock, go to the Gnome Do preferences and in the Appearance tab, select Docky as the Theme. You will also like to tick the "Start Gnome Do at login" in the General tab. You can find great plugins in the Plugins tab.

Comments are welcome.
