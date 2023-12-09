---
title: "[HOWTO] Convert Ubuntu 10.04 Lucid Lynx to Linux Mint 9 Isadora"
date: "2010-08-20"
categories: 
  - "isadora"
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "linux-mint"
  - "linuxmint"
  - "mintmenu"
---

Since Linux Mint 9 Isadora is based completely on Ubuntu 10.04 Lucid Lynx, you can add Linux Mint repository to Lucid and make it look and feel like Linux Mint (additionally you may have to do more than just mint specific applications such as changing themes and tweaking panel but you get the idea). You may also like to install a few components that you like in Linux Mint, for example just the mintmenu or mint-flashplugin-64 (if you want a 64bit version of flash for your 64bit version of Ubuntu).

To do this, just launch Synaptic Package Manager from System>Administration menu and open up Settings>Repositories. In 'Ubuntu Software' tab, make sure you have Universe and Multiverse selected. Then go to Other Software and add the following lines one by one:

deb http://packages.linuxmint.com/ isadora main upstream import
deb http://archive.canonical.com/ubuntu/ lucid partner
deb http://packages.medibuntu.org/ lucid free non-free

Close the Repositories window and click Reload. When done, you will get the following gpg errors:

> W: GPG error: http://packages.linuxmint.com isadora Release: The following signatures couldn't be verified because the public key is not available: NO\_PUBKEY 3EE67F3D0FF405B2 W: GPG error: http://packages.medibuntu.org lucid Release: The following signatures couldn't be verified because the public key is not available: NO\_PUBKEY 2EBC26B60C5A2783

To get rid of these the next time you reload, search for linuxmint-keyring and medibuntu-keyring in Synaptic and install them. Next time you reload or try to install software from Linux Mint, you won't get gpg/authentication errors.

To install a mint software, just search and install it. For example, to install mintmenu, search for it, mark for installation and apply. When done, just add the menu to panel (Right Click Panel>Add to Panel>mint-menu).

To install everything, just mark the meta package mint-meta-main (for 32 bit) or mint-meta-64 (for 64-bit). That should mark everything that Linux Mint has by default. That includes codecs, java and flash and much more. It also includes other default applications such as pidgin, thunderbird and gimp. You can go to 'Custom Filters' (low left hand corner in Synaptic) > Marked Changes (upper right pane) to unmark any applications you don't wish to install. Also, click on 'Mark All Upgrades' and

After installation, tweak it to your liking to make it look the way Linux Mint does or just the way you like it.

Hope this helps.
