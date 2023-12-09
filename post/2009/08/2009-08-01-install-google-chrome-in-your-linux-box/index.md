---
title: "[HOWTO]Install Google Chrome in your Ubuntu 9.04 Jaunty Jackalope and Enable Flash on It"
date: "2009-08-01"
categories: 
  - "jaunty-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "9-04"
  - "9-10"
  - "firefox"
  - "firefox-3-5"
  - "flash"
  - "google-chrome"
  - "google-chrome-os"
  - "jaunty"
  - "jaunty-jackalope"
  - "karmic"
  - "karmic-koala"
  - "linux"
  - "swiftfox"
  - "ubuntu"
  - "youtube"
---

I have Ubuntu 9.04 Jaunty Jackalope 64bit and wanted to give Google Chrome Browser a try to see what it feels like to be running [Google Chrome OS](http://googleblog.blogspot.com/2009/07/introducing-google-chrome-os.html "Google Chrome OS - Upcoming Operating System From Google") (which will be based on Linux and run Google  Chrome Browser).

UPDATE Nov 21: Just adding the repository: deb http://dl.google.com/linux/deb/ stable main will let you install Google Chrome right from Synaptic.

UPDATE: Now I have Ubuntu Karmic Koala (9.10) alpha 4 and same works for Karmic too.

So I headed over to [Google Chrome Linux Page](http://www.google.com/chrome/intl/en/linux.html "Google Chrome Linux"). Since Google Chrome for Linux is under development and public releases has not been made, I headed to [Developer Channel Version Page](http://dev.chromium.org/getting-involved/dev-channel "Google Chrome Developer Channel Version"). Then, I downloaded the [Dev channel (for 64-bit systems)](http://www.google.com/chrome/intl/en/eula_dev.html?dl=unstable_amd64_deb "Download Google Chrome For Ubuntu/Debian 64bit") and then installed it. If you have a 32-bit processor or 32-bit OS, you will need to download the [32 bit version](http://www.google.com/chrome/intl/en/eula_dev.html?dl=unstable_i386_deb "Download Google Chrome for 32bit Ubuntu\Debian based systems"). I double clicked the downloaded deb file to install it and it was available in the Applications > Internet menu.

UPDATE: For Karmic Koala except for installing deb package as gdebi-gtk crashes (this bug) when trying to install this package. To install, you should use sudo dpkg-i packagename.deb from the terminal to install.

On first launch, it asked me if I wanted to import settings and history from Firefox and I chose to. It is good enough so far. I am using it to post this thread too.

However, flash has not been enabled and I could not play videos on Youtube. So to install and enable it, just type in the following commands (you must have flash plugin installed in Firefox for the following commands to work). Open op the terminal and copy\\paste or type in the following commands: `sudo mkdir -p /opt/google/chrome/plugins sudo cp /usr/lib/flashplugin-installer/libflashplayer.so /opt/google/chrome/plugins/ /opt/google/chrome/google-chrome --enable-plugins` Source: http://jeanderuelle.blogspot.com/2009/07/enable-flash-on-google-chrome-linux-dev.html

UPDATE: You will need to append `--enable-plugins at the end of the launcher or menu item if you want it to load with flash plugin enabled each time you launch Chrome.`

It is lot faster and lighter than Firefox 3.5 and [Swiftfox](http://getswiftfox.com/ "Swiftfox - Firefox Compiled for Your Processor"). Of course, I miss the add-ons in Chrome and will still use Swiftfox as the default browser.
