---
title: "[HOWTO] Install VLC Media Player 1.1 in Ubuntu Lucid Lynx and Maverick Meerkat"
date: "2010-06-15"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "1-1"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "maverick"
  - "maverick-meerkat"
  - "meerkat"
  - "vlc"
---

One of the most popular media players, VLC Media Player has version 1.1 RC out. The final version should be released shortly. You can install the Release Candidate by installing the following PPA:

ppa:c-korn/vlc

To do that, open System>Administration>Synaptic Package Manager>Settings>Repositories>Other Software>Add and paste in the code above. If you are on Maverick, since the PPA does not have packages for Maverick, you can install the Lucid packages by editing the added PPA and changing maverick to lucid. Then close the Repository window and Reload. Then Mark for updates and Apply. That should install the latest vlc packages.
