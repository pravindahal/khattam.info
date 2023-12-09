---
title: "[SOLVED] Sound Problem in Ubuntu 9.10 (Karmic Koala Alpha 4) due to Pulseaudio"
date: "2009-09-09"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "9-10"
  - "jaunty"
  - "karmic"
  - "karmic-koala"
  - "koala"
  - "linux"
  - "problem"
  - "pulseaudio"
  - "ubuntu"
---

Sound in my Ubuntu Karmic Koala desktop used to freeze and I was into real problem. The process "pulseaudio" used to hog the CPU and sound would stop at times. So I replaced it with esound and it is fine now. This is how I did it.

Lanched Synaptic (System>Administration>Synaptic Package Manager) and then searched for pulseaudio. Then right clicked on it and then Marked it for Complete Removal. Then searched for esound and then Marked it for installation. If it is already installed, you may want to Mark it for reinstallation.

Hope this helps.
