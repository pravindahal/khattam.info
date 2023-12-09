---
title: "[HOWTO] Make Firefox fast and more responsive"
date: "2009-09-13"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "faster"
  - "firefox"
  - "firefox-3-5"
  - "karmic"
  - "kubuntu"
  - "linux"
  - "responsive"
  - "ubuntu"
---

I use Firefox 3.5.3 for my day to day browsing on my Ubuntu Karmic Koala Alpha (with KDE 4.3) and recently I experienced tremendous slowdowns making it less fit for use. I use a lot of addons including Firebug and Greasemonkey and it is no surprise that Firefox is slower than one without any extensions. I cannot move to Google Chrome or Epiphany because of the dependency on various add-ons such as Adblock Plus, Lastpass, Greasemonkey, Firebug and others and so I had to look what I can do.First and foremost, I thought the theme I was using (Default theme on Kubuntu) was one of the problems and thus I got [this theme called iFox Smooth](https://addons.mozilla.org/firefox/addon/1830 "iFox Smooth") theme instead. Not only it looks nicer, that solved half of my problem. After I restarted Firefox, I felt like I was using Google Chrome or Epiphany. It is really smooth.

Then, I went on to History (Edit>Preferences>Privacy on Linux and maybe Tools>Preferences on Windows). If you use Lastpass or other password manager and bookmark what you need, you will probably not require History. You can disable it or change settings to maintain history for just or few days or disable history completely by checking the "Clear History When Firefox Closes". This should improve load times and overall performance of Firefox. But make sure you know what you are doing.

Also, you can disable add-ons you rarely use and enable only when required. Also uninstall add-ons you don't use at all. I did. You know how they can accumulate over time and we fail to acknowledge that we've had more than enough.

And you have probably heard a lot about tweaking network parameters of Firefox via about:config, so I am not going to talk about that here. Find it [somewhere else](http://hubpages.com/hub/Free-Tips-How-To-Make-Firefox-Respond-Faster).

Also, some people also insist on changing the content.switch.threshold to 100000 to make Firefox more responsive, but I barely felt a difference. However, you can give it a try too.

Other Information: If you are on Windows, you may try [SpeedyFox](http://www.crystalidea.com/speedyfox "Speedy Fox"). I have not tried it though, but some of my friends say it works. This is not benificial if you opted to keep no history though. If you are on Windows, slowing down of overall system (including firefox) may probably be due to viruses. make sure you run latest antivirus with latest update definitions.

Hope this was helpful.
