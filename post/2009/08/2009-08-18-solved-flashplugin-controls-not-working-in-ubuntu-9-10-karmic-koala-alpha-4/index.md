---
title: "[SOLVED]: flashplugin Controls not Working in Ubuntu 9.10 Karmic Koala"
date: "2009-08-18"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "9-10"
  - "firefox"
  - "firefox-3-5"
  - "flash"
  - "flash-plugin"
  - "flashplugin"
  - "karmic"
  - "karmic-koala"
  - "linux"
  - "mozilla"
  - "ubuntu"
  - "web"
  - "youtube"
---

Please find the latest post [here](http://www.khattam.info/2010/05/17/solved-adobe-flashplugin-problem-in-ubuntu-10-04-lucid-lynx-64bit).

UPDATE Nov 2, 2009: If you want to make flash work normal in 64-bit Ubuntu 9.10 Karmic Koala, the following commands shall help. So start your terminal and get going:

sudo apt-get remove flashplugin-installer flashplugin-nonfree swdec-mozilla mozilla-plugin-gnash
cd /tmp
wget http://download.macromedia.com/pub/labs/flashplayer10/libflashplayer-10.0.32.18.linux-x86\_64.so.tar.gz
tar xf libflashplayer-10.0.32.18.linux-x86\_64.so.tar.gz
sudo mv libflashplayer.so /usr/lib/mozilla/plugins/

and restart firefox. If this does not work or you want to keep track of what has happened here, read on.

UPDATE Nov 2, 2009: The problem persisted for me even after I upgraded to the latest version. Using 64-bit flash plugin from [Adobe Labs](http://labs.adobe.com/downloads/flashplayer10.html "Adobe Labs") helps for me now. For this you will need to download the latest plugin from [http://labs.adobe.com/downloads/flashplayer10.html](http://labs.adobe.com/downloads/flashplayer10.html "Adobe Labs") and extract it to /home/YOUR\_USER\_NAME/.mozilla/plugins or /usr/lib/mozilla/plugins. If you intend to extract it to /usr/lib/mozilla/plugins then you will need root privileges. One way of getting root privileges is launching nautilus as "gksu nautilus /usr/lib/mozilla/plugins" in the Run Application dialog (Alt+F2). Then copy the extracted libflashplayer.so in that directory and restart Firefox.

UPDATE: I had problems with swfdec-gnome also. When I used to close any tabs with active flash content, firefox would simply crash. I removed it and installed flashplugin via flashplug-installer (in synaptic) and now it is working fine. I disabled some plugins and maybe thats what worked. Not sure. Anyone came up with whats actually happening?

ORIGINAL POST 10 Aug, 2009: I recently installed Karmic Koala (Ubuntu 9.10) alpha 4 amd64 version and have been facing problem with flashplugin for Firefox 3.5. The flashplugin is a large download (as it depends on 32 bit libraries.. they have 32 bit version of the plugin now in amd64 too) and does not work well with YouTube videos, the flash applications do not respond user clicks. I have removed flashplugin via Synaptic Package Manager and installed swfdec-mozilla instead (firefox restart required after you do). This one has worked fine for me till now.

Hope this was helpful. Hope this is solved in the stable release.

Thanks to "Fatal Toenail Infection".
