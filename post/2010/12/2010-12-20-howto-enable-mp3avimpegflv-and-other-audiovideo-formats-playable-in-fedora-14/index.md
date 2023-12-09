---
title: "[HOWTO] Enable MP3/AVI/MPEG/FLV and other audio/video formats playable in Fedora 14"
date: "2010-12-20"
tags: 
  - "amarok"
  - "fedora"
  - "kde"
  - "linux"
  - "livna"
  - "rpm-fusion"
  - "smplayer"
  - "vlc"
---

I just installed Fedora 14 KDE Spin and like many other Linux distros, it does not play MP3, MPEG and several other formats by default. To enable playback of these proprietary formats, you must install non-free codecs. To get those, I installed the [Livna](http://rpm.livna.org/) and [RPM Fusion](http://rpmfusion.org) repos by clicking the following links and opening each with KPackageKit: [Livna](http://rpm.livna.org/livna-release.rpm) [RPM Fusion Free](http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-stable.noarch.rpm) [RPM Fusion Non-Free](http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-stable.noarch.rpm)

Wait for them to be installed and when done search KPackageKit for SMplayer and VLC. For audio playback, you can install a great KDE Audio Player known as Amarok. You can play almost any format with VLC but you might want to keep another player handy for playback. To enable almost any media support for Amarok and SMplayer, you must install gstreamer-plugins-bad and gstreamer-plugins-ugly and xine-lib-extras-freeworld.

Hope this helps.
