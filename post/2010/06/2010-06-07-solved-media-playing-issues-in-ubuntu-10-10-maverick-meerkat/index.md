---
title: "[SOLVED] Media Playing issues in Ubuntu 10.10 Maverick Meerkat"
date: "2010-06-07"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-10"
  - "avi"
  - "linux"
  - "lucid"
  - "maverick"
  - "maverick-meerkat"
  - "totem"
  - "ubuntu"
  - "ubuntu-10-10"
  - "vlc"
  - "xvid"
---

I am using Ubuntu 10.10 Maverick Meerkat 64bit Alpha 1 and I have been facing problem playing AVI and FLV files. I used to get the the following error "No suitable decoder module: VLC does not support the audio or video format "XVID". VLC Unfortunately there is no way for you to fix this." in VLC when I tried to play some AVI files. Also, in terminal, it said: "main decoder error: no suitable decoder module for fourcc \`XVID'. VLC probably does not support this sound or video format." Also, FLV files failed to play without any error. Totem said: "No packages with requested plugins found. The requested plugins are: XVID MPEG-4 decoder/H.264 decoder".

The problem was with libavcodec and libavutil. It can be fixed by removing all of libavutilxx (libavutil50, libavutil49, libavutil-extra-49, libavutil-extra-50) and reinstalling only what is required. This may also remove other packages (vlc for example, if you have it installed that is), so watch out but don't install them immediately. Exit Synaptic. Now, if you want to fix totem, just open media with it. It should ask you for codecs, install them. Totem should start working. Install vlc later.

Hope this helps.
