---
title: "[HOWTO] Add multiple rapidshare, megaupload downloads in a Queue in Ubuntu with Tucan Manager"
date: "2010-02-05"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "4shared"
  - "automatic-captcha"
  - "badongo"
  - "captcha"
  - "depositfiles"
  - "download"
  - "easy-share"
  - "filefactory"
  - "gigasize"
  - "hotfile"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "mediafire"
  - "multiple"
  - "queue"
  - "rapidshare"
  - "rapidshare-downloader"
  - "sendspace"
  - "ubuntu"
  - "upload"
  - "uploading"
  - "zshare"
---

My friend who recently switched to Ubuntu was looking for a rapidshare, megaupload file downloader where he can queue downloads and leave it to download. Actually I found an application that not only supports rapidshare and megaupload but lots of other file-sharing sites such as 4shared, badongo, depositfiles, easy-share, filefactory, gigasize, hotfile, mediafire, sendspace, uploading and zshare. The application is called Tucan Manager and is available from the universe repository in Lucid Lynx (I'm sure it is available in Karmic and older versions too). Moreover, it supports uploads to these sites too.  
  
To install it, just launch synaptic (System> Administration> Synaptic Package Manager). Goto settings>repositories and make sure "Community maintained opensource software (universe)" is checked. Reload the software list by clicking on reload and wait till it is done. Search for tucan and mark it for installation. Install it by selecting apply and wait till it is installed.  
  
Once it is installed, close synaptic and launch it from Applications>Internet>Tucan Manager (or Alt+F2>tucan) and click on Find on the preferences window. Get the updates and mark the services you wish to use. Close it and restart it again.

Now, just Add the links. You may add multiple links at once. I checked it with megaupload and it automatically processed CAPTCHA so I didn't need to do anything else. By default, it downloads to your home directory (Places>Home).

You may wish to change preferences and make it close to tray (Advanced Configuration) and make other changes as you please.

I don't download much from these sites, but someone who needs might find this useful. I haven't used much of this application as I just tested it and I wont use it much. Whoever does, please do share your experience.
