---
title: "[HOWTO] Change GDM 3 Theme and Wallpaper"
date: "2010-11-14"
categories: 
  - "debian-linux"
tags: 
  - "gdm3"
  - "linux"
  - "theme"
  - "wallpaper"
---

I am using Debian Squeeze Testing and I have gdm3 installed.  I wanted to change the default gdm theme and here is how I did it.

I opened the file /usr/share/gdm/greeter-config/20\_debian in a text editor as root and changed the line containing "/desktop/gnome/background/picture\_filename" and gave the full path to the new location of wallpaper. I also changed the line containing "/desktop/gnome/interface/gtk\_theme" and wrote the name of theme instead of the default (in my case it was Clearlooks and I changed it to an installed theme Equinox). Then I saved the file and logged out to see the changes.

While changing the theme, make sure that the theme is installed as available to all users (i.e. in /usr/share/themes).
