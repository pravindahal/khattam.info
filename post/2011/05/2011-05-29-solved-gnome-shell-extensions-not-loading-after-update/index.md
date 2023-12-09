---
title: "[SOLVED] Gnome shell extensions not loading after update"
date: "2011-05-29"
tags: 
  - "extensions"
  - "fedora"
  - "gnome-shell"
  - "linux"
---

I have Fedora 15 with Gnome Shell and I found that after the last update, I found that Gnome Shell extensions were not working. I ran lg (Alt+F2 and type in "lg" without quotes and press enter) and in the error tab, I could see version mismatch error. I found that gnome-shell had been updated while the extensions were not. As a temporary fix, I tried editing metadata.js in extension folder (/usr/share/gnome-shell/extensions/_extension-name_) of the extension in question by entering proper gnome-shell version (which can be found by running gnome-shell --version in the terminal) and it worked.
