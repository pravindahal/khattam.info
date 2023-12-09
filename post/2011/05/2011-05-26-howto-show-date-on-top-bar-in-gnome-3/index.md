---
title: "[HOWTO] Show date on top bar in Gnome 3"
date: "2011-05-26"
tags: 
  - "date"
  - "fedora"
  - "gnome-3"
  - "linux"
---

I have installed Fedora 15 with Gnome 3. In the top bar, only day and time is shown. If you want the date to be shown as well, open terminal and run the following command:

gsettings set org.gnome.shell.clock show-date true

The changes are instant and you should see date right away.
