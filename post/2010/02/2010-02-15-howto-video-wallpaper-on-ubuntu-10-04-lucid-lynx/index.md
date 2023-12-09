---
title: "[HOWTO] Video Wallpaper on Ubuntu 10.04 Lucid Lynx with Shantz XWinWrap"
date: "2010-02-15"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "desktop-background"
  - "desktop-wallpaper"
  - "hardy"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "shantz-xwinwrap"
  - "ubuntu"
  - "video-as-desktop"
  - "video-desktop"
  - "video-wallpaper"
  - "windows"
  - "xwinwrap"
---

I wanted to try out video wallpaper (like DreamScene on Windows 7). I had tried XWinWrap with Hardy but back then, I had problems running Compiz on an old PC and it did not look good at all. Now, I am trying it out on a new PC and Compiz works well on my onboard Intel GMA 3000 on Ubuntu 10.04 Lucid Lynx Alpha.

If you want to try this, you must have compiz enabled. You may also want to install mplayer and codecs for videos you want to use as desktop background.

First of all, I downloaded Shantz XWinWrap from [here](http://tech.shantanugoel.com/projects/linux/shantz-xwinwrap). I extract it and installed it. You can use the deb files for your respective architecture. I chose i386 as I have 32-bit version of Lucid installed.

Once it is installed, you can open up the terminal and then try running the following command to see how it works:

xwinwrap -ni -argb -fs -s -st -sp -nf -b -- /usr/lib/xscreensaver/glmatrix -window-id WID

You can exit it by pressing Ctrl+C in terminal.

Then, I tried with mplayer. First, you may want to set mplayer to play on loop by default, otherwise mplayer will exit when it is done playing the video and so will XWinWrap. To enable repeat mode in mplayer by default, edit /home/Your\_User\_Name/.mpalyer/config and add

loop=0

at the end of the file. To do that, press Alt+F2 and then type in

gedit .mplayer/config

, add

loop=0

at the end and save it.

After that was done, I tried the following in terminal:

xwinwrap -ni -o 0.9 -fs -s -st -sp -b -nf -- mplayer -wid WID -nosound /full/path/to/video.mpg

Notice the option "-o 0.9", this is the opacity of the video wallpaper. If you do not use opacity option (use -o 1.0 or omit -o option), you will not be able to see icons on the Desktop. If you have set it to be transparent, you may want to blank the Desktop with a solid color. Black background works good for most of the videos, but I recommend you tweak the color and opacity values so that it looks good enough.

You can find videos for wallpaper at [Dreamscene.org](http://dreamscene.org)

If you want the video desktop to be retained when you next log on, you will need to enable it at startup. You can do so by adding the command you used in System>Preferences>Startup Application.

Please share your "Wallpaper as Video" experience.
