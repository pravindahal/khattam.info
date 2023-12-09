---
title: "[HOWTO] Get rid of unwanted and duplicate entries in \"Open With\" in Linux"
date: "2010-11-16"
tags: 
  - "linux"
  - "open-with"
---

When I right click on files/directories and click on "Open with another application", I get a lot of duplicate entries and unwanted applications (like Wine applications I don't have anymore, Minefield browser which I removed a long time ago, duplicate entries for Geany etc.). To remove them, I opened up my ~/.local/share/applications/ by pressing Alt+F2 and typing in

.local/share/applications/

Then, I just removed the files with names like "wine-extension-X.desktop" and all wine entries were gone. You can choose to keep some if you have Wine installed and want then to appear in "Open With". I also removed Minefield and Geany duplicate entries that I did not need. I also removed other files with "userapp" and "usercustom" in the names which I did not need anymore. That removed all the unwanted entries and my "Open With" box is clutter free again.
