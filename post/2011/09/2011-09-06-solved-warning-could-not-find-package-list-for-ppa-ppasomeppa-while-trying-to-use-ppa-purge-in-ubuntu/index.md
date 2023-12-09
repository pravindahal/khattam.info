---
title: "[SOLVED] \"Warning:  Could not find package list for PPA: ppa:some/ppa\" while trying to use ppa-purge in Ubuntu"
date: "2011-09-06"
categories: 
  - "ubuntu-linux"
tags: 
  - "gnome3"
  - "linux"
  - "ppa"
  - "ppa-purge"
---

When trying to purge Gnome3 PPA, I had to cancel the ppa-purge process and when I tried to run the same, I got the following message:

> Updating packages lists PPA to be removed: gnome3-team gnome3 Warning: Could not find package list for PPA: gnome3-team gnome3

I had to add the PPA again to be able to successfully run ppa-purge. For example, if your ppa is ppa:gnome3-team/gnome3, you should run the following:

apt-add-repository ppa:gnome3-team/gnome3

Then you should be able to run ppa-purge again.

Note: In my case, I also got the following error after adding the PPA again:

> E: Type 'ain' is not known on line 3 in source list /etc/apt/sources.list.d/gnome3-team-gnome3-natty.list E: The list of sources could not be read. Warning: apt-get update failed for some reason PPA to be removed: gnome3-team gnome3 Warning: Could not find package list for PPA: gnome3-team gnome3

This seems to be some bug. I had to manually edit /etc/apt/sources.list.d/gnome3-team-gnome3-natty.list and remove the line containing 'ain'. This should not be required in your case.

If this does not work, you should check if the PPA exists at all and if you have packages installed from that PPA.
