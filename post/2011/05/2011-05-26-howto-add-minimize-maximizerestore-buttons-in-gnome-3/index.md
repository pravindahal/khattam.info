---
title: "[HOWTO] Add Minimize, Maximize/Restore buttons in Gnome 3"
date: "2011-05-26"
tags: 
  - "fedora"
  - "fedora-15"
  - "gnome-3"
  - "linux"
  - "maximize"
  - "minimize"
---

I am using Fedora 15 with Gnome 3. The window title bars have only a Close button as control button. If you want to add other buttons here is what you need to do.

### 1\. Install Configuration Editor

You can skip to step 2 if you have Configuration Editor installed.  
Press Super (Windows) key and type **Add/Remove** and open **Add/Remove Software**.  
Search for **gconf-editor** and install it. You may need to wait a while if you are using **Add/Remove Software** for the first time.

### 2\. Use Configuration Editor to change button layout

Launch **Configuration Editor**.  
In the **Configuration Editor** navigate to **desktop**\>**gnome**\>**shell**\>**windows**  
Find button\_layout and enter the following to add Minimize and Maximize buttons:

:minimize,maximize,close

If you want Ubuntu-like control box, enter the following instead:

close,minimize,maximize:

### 3\. Restart Shell or re-login

The changes are not instant. You either need to restart Gnome shell using Alt+F2 > r > ENTER (as reader Elliot pointed out in the comments) or you need to log out and log back in to see the changes.

Hope this helps.
