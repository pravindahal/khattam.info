---
title: "[SOLVED] Can't open /dev/dsp in Ubuntu 10.10 Maverick Meerkat and Lucid Lynx 10.04"
date: "2010-06-08"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "devdsp"
  - "alsa"
  - "alsa-oss"
  - "linux"
  - "oss"
  - "oss-compat"
  - "padsp"
  - "pulseaudio"
  - "sbagen"
---

I recently installed a program called SBaGen which uses device /dev/dsp to output audio. However, the OSS (Open Sound System) device is not available anymore in Lucid and Maverick (maybe it doesn't work with older versions, but I'm not sure), not even with OSS emulation with alsa. The snd-pcm-oss module does not load even when oss-compat and alsa-oss have been installed. It is seen to be blacklisted in /etc/modprobe.d/alsa-base.conf.

However, pulseaudio also supports OSS emulation with an app called padsp. So, for example if you want to launch

sbagen examples/basics/prog-chakras-1.sbg

you should launch

padsp sbagen examples/basics/prog-chakras-1.sbg

This way, you will be able to run OSS based sound apps without need for OSS.
