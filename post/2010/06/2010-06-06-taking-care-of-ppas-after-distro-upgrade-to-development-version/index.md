---
title: "[HOWTO] Take care of PPAs after Distro upgrade to Development version"
date: "2010-06-06"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "10-10"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "maverick"
  - "maverick-meerkat"
  - "merecat"
  - "merekat"
  - "ubuntu"
---

I recently upgraded to Ubuntu 10.10 Maverick Meerkat Alpha 64bit and as expected, the PPAs that I use have been disabled. When I enable them, I get 404 errors for most because they have not set up PPA for Maverick yet. But I need the packages, I need the updates to those packages.

To get them, all I need to do is edit them in Repositories > Other software. Here I just change maverick to lucid and then I can use and update those packages. If I later find that the maintainers have already set one up for Maverick, I can simply change lucid to maverick.

If you want to add a PPA that does not have a Maverick release, lets say deluge-team ppa which does not have packages for Maverick at the time of writing this, you can simply add ppa:deluge-team/ppa and then edit it to change maverick to lucid. That should do it.

This is not a recommended procedure but it works and has always worked for me.
