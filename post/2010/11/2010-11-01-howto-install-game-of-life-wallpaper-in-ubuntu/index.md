---
title: "[HOWTO] Install Game Of Life Wallpaper in Ubuntu"
date: "2010-11-01"
categories: 
  - "ubuntu-linux"
tags: 
  - "game-of-life"
  - "linux"
  - "wallpaper"
---

[Game of Life Wallpaper](http://github.com/azizmb/Game-of-Life-Wallpaper) is an ever changing wallpaper which is supposed to simulate Conways Game of Life. It was [featured in OMG Ubuntu](http://www.omgubuntu.co.uk/2010/10/live-wallpaper-game-of-life/), recently.

Here is how it can be installed in Ubuntu.

**Install dependencies** Open up the terminal and run the following to install python-numpy and python-scipy:

sudo apt-get install python-numpy python-scipy

Run the following to install git:

sudo apt-get install git

**Download Source Code** Run the following to get the latest source codes:

git clone http://github.com/azizmb/Game-of-Life-Wallpaper.git

**Configure and Generate Wallpapers** Now, cd to Game-of-Life-Wallpaper

cd Game-of-Life-Wallpaper

Then, open the configuration files with gedit:

gedit config.py

Find the section "screen resolution" and make necessary changes based on your Desktop resolution. Save and Close gedit and come back to terminal. Now, run gol.py to generate the wallpapers:

python gol.py

Once done, you will see message like this one:

> Done! You can now set the wallpaper by selecting '/home/username/path/Game-of-Life-Wallpaper/demos/achimsp144\_106/achimsp144\_106.xml' as the wallpaper.

Note the part that looks like "/home/username/path/Game-of-Life-Wallpaper/demos/achimsp144\_106/achimsp144\_106.xml", and go to Appearance Preferences > Background (Right click on desktop > Change Desktop Background) and then click Add, then navigate to that XML file and set it as Desktop.

Hope this helps.
