---
title: "[HOWTO] Install Firefox 4 in Ubuntu 10.04 Lucid Lynx and 10.10 Maverick Meerkat"
date: "2011-04-06"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "firefox"
  - "firefox-4"
  - "linux"
  - "lucid-lynx"
  - "maverick-meerkat"
  - "ubuntu"
---

Firefox 4 has been released recently and it is not available via update manager in Ubuntu 10.04 Lucid Lynx and 10.10 Maverick Meerkat. The [Ubuntu Mozilla Daily Build PPA](https://launchpad.net/~ubuntu-mozilla-daily/+archive/ppa) provides it but it always the latest daily build and not the stable version.

For stable version, you can use [Firefox Stable PPA](https://launchpad.net/~mozillateam/+archive/firefox-stable). To install the PPA in Lucid or Maverick, just launch Synaptic (System>Administration>Synaptic Package Manager) and then go to Settings>Repositories>Other Software. Now click Add and paste in the following:

ppa:mozillateam/firefox-stable

Close the Repositories window and then click reload. When it is done, search for firefox-4.0-gnome-support and mark it for installation. It should mark other required packages. Apply and wait for installation to finish.
