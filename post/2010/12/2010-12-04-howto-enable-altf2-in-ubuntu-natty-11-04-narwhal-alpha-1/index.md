---
title: "[HOWTO] Enable Alt+F2 in Ubuntu Natty 11.04 Narwhal Alpha 1"
date: "2010-12-04"
categories: 
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "altf2"
  - "ccsm"
  - "compiz"
  - "compizconfig-settings-manager"
  - "gmrun"
  - "linux"
---

If you have installed Ubuntu Natty Narwhal Alpha 1, you will notice the new Unity interface and hence no Gnome Panel(s) anymore. Since "Run Application" dialog is a part of gnome-panel, it is not possible to enable the same "Run Application" dialog. If you wish, you can achieve that by running the gnome-panel, but this is not the recommended course of action if you wish to keep running unity.  
So, the other way to make it work is to use third party run dialogs from repositories. One of the best run dialog is gmrun. It is available in Ubuntu universe repositories. Open up the terminal (by pressing Ctrl+Alt+T) and type in the following to launch Synaptic Package Manager:

sudo synaptic

Then, go to Settings>Repositories and Enable the Universe repository.  
  
After having done that, close the repository window and synaptic. In the terminal, type in the following:

sudo apt-get update
sudo apt-get upgrade
sudo apt-get install gmrun compizconfig-settings-manager

Now, lets launch compizconfig-settings-manager. Just type in the following in the terminal:

ccsm

Search for commands and enable it. Click on Commands to set commands and Key Bindings. In Command line 0, type in gmrun and in Key Bindings tab, click on the Disabled button and check Enable to Enable it. Press the Grab key combination button and press Alt+F2. In the dialog that pops up, click "Disable Run Applications".

If all goes well, you can now press Alt+F2 and a "Run Program" dialog will pop up. You can use tab to complete fields and press Ctrl+R to search older run entries.

Hope this helps.
