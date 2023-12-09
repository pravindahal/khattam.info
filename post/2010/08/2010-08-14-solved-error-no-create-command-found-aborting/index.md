---
title: "[SOLVED] ERROR: No create command found. Aborting."
date: "2010-08-14"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "quickly"
---

I was thinking of trying out quickly in my Ubuntu 10.10 Maverick Meerkat and tried:

quickly create ubuntu-application foo

in the terminal, but I got this:

ERROR: No create command found.
Aborting.

I then found out that I had not installed the package quickly-ubuntu-template. I did it and it solved my problem. If you already have that installed and are still getting the problem, view comments in the bug report: https://bugs.launchpad.net/quickly/+bug/519222/

Hope this helps.
