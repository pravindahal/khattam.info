---
title: "[SOLVED] Could not create a python ScriptEngine for the [name-of-plasmoid] widget"
date: "2010-12-20"
tags: 
  - "fedora"
  - "linux"
  - "plasmoid"
  - "plasmoidviewer"
---

I recently installed Fedora 14 KDE Live Spin and am trying to get my hands into plasmoid development. I picked python as a language of choice but was getting the following error while trying to run plasmoids:

> The object could not be created for the following reason: **Could not create a python ScriptEngine for the \[name-of-plasmoid\] widget.**

I checked if PyQT4, PyKDE4 and kdebase-workspace-python-applet were installed and they were but I was still getting the errors. I had almost given up but then I realized that I had just upgraded a lot of packages. So, I just rebooted and I was able to add plasmoids without problems. If you are getting this error, you must check if you can run the plasmoid with plasmoidviewer from the terminal and check for errors in the terminal. Hope this helps.
