---
title: "[SOLVED] \"No packages with the requested plugins found\" while playing WMV Totem in Debian Squeeze"
date: "2010-11-16"
categories: 
  - "debian-linux"
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "medibuntu"
  - "mplayer"
  - "totem"
  - "vlc"
  - "w32codecs"
  - "w64codecs"
  - "win32-codecs"
  - "wmv"
---

I was trying to play a video with Totem in Debian Squeeze Testing and got the following error and only video played.

> **No packages with the requested plugins found** The requested plugins are: Windows Media Audio 9 decoder

I have the available codecs installed. I installed Smplayer from the repos but still did not get audio. I even installed vlc player but it didn't help either. I got the following error with mplayer command line:

> MPlayer 1.0rc3-4.4.4 (C) 2000-2009 MPlayer Team mplayer: could not connect to socket mplayer: No such file or directory Failed to open LIRC support. You will not be able to use your remote control.
> 
> Playing DSC0123.WMV. ASF file format detected. \[asfheader\] Audio stream found, -aid 1 \[asfheader\] Video stream found, -vid 2 VIDEO: \[WMV3\] 1280x720 24bpp 1000.000 fps 5000.0 kbps (610.4 kbyte/s) Clip info: name: author: copyright: comments: open: No such file or directory \[MGA\] Couldn't open: /dev/mga\_vid open: No such file or directory \[MGA\] Couldn't open: /dev/mga\_vid \[VO\_TDFXFB\] This driver only supports the 3Dfx Banshee, Voodoo3 and Voodoo 5. \[VO\_3DFX\] Unable to open /dev/3dfx. ========================================================================== Opening video decoder: \[dmo\] DMO video codecs Win32 LoadLibrary failed to load: wmv9dmod.dll, /usr/lib/codecs/wmv9dmod.dll, /usr/lib/win32/wmv9dmod.dll, /usr/local/lib/win32/wmv9dmod.dll IMediaObject ERROR: 0x83e8e2c could not open DMO DLL (0x0 : 0) Failed to create DMO filter ERROR: Could not open required DirectShow codec wmv9dmod.dll. You need to upgrade/install the binary codecs package. Go to http://www.mplayerhq.hu/dload.html VDecoder init failed :( Opening video decoder: \[dmo\] DMO video codecs Win32 LoadLibrary failed to load: wmvdmod.dll, /usr/lib/codecs/wmvdmod.dll, /usr/lib/win32/wmvdmod.dll, /usr/local/lib/win32/wmvdmod.dll IMediaObject ERROR: 0x83e8e2c could not open DMO DLL (0x0 : 0) Failed to create DMO filter ERROR: Could not open required DirectShow codec wmvdmod.dll. You need to upgrade/install the binary codecs package. Go to http://www.mplayerhq.hu/dload.html VDecoder init failed :( Opening video decoder: \[ffmpeg\] FFmpeg's libavcodec codec family Selected video codec: \[ffwmv3\] vfm: ffmpeg (FFmpeg WMV3/WMV9) ========================================================================== ========================================================================== Opening audio decoder: \[dmo\] Win32/DMO decoders Win32 LoadLibrary failed to load: wma9dmod.dll, /usr/lib/codecs/wma9dmod.dll, /usr/lib/win32/wma9dmod.dll, /usr/local/lib/win32/wma9dmod.dll IMediaObject ERROR: 0x83e8e2c could not open DMO DLL (0x0 : 0) ERROR: Could not open required DirectShow codec wma9dmod.dll. ADecoder preinit failed :( ADecoder init failed :( Opening audio decoder: \[dmo\] Win32/DMO decoders Win32 LoadLibrary failed to load: wmadmod.dll, /usr/lib/codecs/wmadmod.dll, /usr/lib/win32/wmadmod.dll, /usr/local/lib/win32/wmadmod.dll IMediaObject ERROR: 0x83e8e2c could not open DMO DLL (0x0 : 0) ERROR: Could not open required DirectShow codec wmadmod.dll. ADecoder preinit failed :( ADecoder init failed :( Cannot find codec for audio format 0x162. Read DOCS/HTML/en/codecs.html! Audio: no sound Starting playback... VDec: vo config request - 1280 x 720 (preferred colorspace: Planar YV12) VDec: using Planar YV12 as output csp (no 0) Movie-Aspect is undefined - no prescaling applied. VO: \[xv\] 1280x720 => 1280x720 Planar YV12 V: 5.5 63/ 63 28% 1% 0.0% 0 0 Exiting... (Quit)

So, I decided to add [Medibuntu repo](http://medibuntu.org/). but it did not list repo for Debian Squeeze in [repos page](http://medibuntu.org/repository.php). I found [Ubuntu Wiki page on Medibuntu](https://help.ubuntu.com/community/Medibuntuhttps://help.ubuntu.com/community/Medibuntu) which has instruction on how to install it on Ubuntu, but the instruction does not work for Debian. So, I edited the command to add Lucid Lynx repos. Just run the following command as root and you will be able to add Medibuntu repos:

wget --output-document=/etc/apt/sources.list.d/medibuntu.list http://www.medibuntu.org/sources.list.d/lucid.list && sudo apt-get --quiet update && sudo apt-get --yes --quiet --allow-unauthenticated install medibuntu-keyring && sudo apt-get --quiet update

After adding the repos, just run the following command (again, as root of course) to install win32 binary codecs (works for 32 bit and 64 bit installation):

apt-get install w\`if \[ 'x86\_64' == \\\`uname -m\\\` \]; then echo 64; else echo 32; fi\`codecs

Now, you should be able to play WMV with sound using mplayer or Smplayer (Totem and Vlc still don't work though).
