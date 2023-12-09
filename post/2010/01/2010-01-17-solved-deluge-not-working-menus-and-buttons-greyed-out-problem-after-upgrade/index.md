---
title: "[SOLVED] Deluge not working (Menus and Buttons Greyed Out) Problem after Upgrade"
date: "2010-01-17"
categories: 
  - "ubuntu-linux"
tags: 
  - "9-10"
  - "deluge"
  - "deluge-gtk"
  - "grey"
  - "greyed"
  - "karmic"
  - "linux"
  - "lost"
  - "torrent"
  - "torrents"
  - "ubuntu"
---

I upgraded deluge recently to version 1.2.0 and then started it. The "Add Torrent" and several other options were greyed out and the torrents I was downloading were not there anymore. Here is how I got around the problem and how you can do it if you are facing the same.

You will need to goto ~/.config/ (i.e. /home/Your\_UserName/.config). It will be hidden, so View > Show Hidden Files in nautilus. And then just rename the deluge folder to something else (say deluge\_backup). Now, launch deluge again. You will see the options are not greyed anymore. But the torrent files are still missing. To get around that, just quit deluge and then from deluge\_backup (or the directory you renamed earlier) copy the directory "state" to the newly created (by deluge program when you launched it) deluge directory. Now launch deluge and it should show the torrents you were downloading. You may also copy other directories like "plugins", if you had plugins installed. But in my case there were none. So it was not a problem.

I was too lazy to find out exactly what caused the problem (which particular file or directory). If anyone does, please do share.

Hope this helps.
