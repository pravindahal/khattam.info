---
title: "[HOWTO] Reset gnome-panel and applets to default"
date: "2010-09-01"
tags: 
  - "applets"
  - "gnome-panel"
  - "linux"
---

If you have messed up gnome-panel settings or applets, you can simply reset it to default. To do so, just run the following commands from the terminal (Alt+F2->gnome-terminal):

gconftool-2 --recursive-unset /apps/panel
killall gnome=panel
