---
title: "[HOWTO] Add Launchpad Ubuntu PPA in Debian Squeeze Testing"
date: "2010-11-13"
categories: 
  - "debian-linux"
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "gpg"
  - "launchpad"
  - "linux"
  - "ppa"
  - "synaptic"
---

I have installed Debian Squeeze Testing replacing Ubuntu 10.10 Maverick Meerkat and miss some applications only available via Launchpad PPAs. Not that they can't be compiled from their sources or installed by downloading debs, but it would be great if updates were available from update manager like in Ubuntu. So I decided to add some Ubuntu PPAs and they are working fine. So, I decided to share here with the hope that it would be helpful to my readers.

If you want to install a PPA in Squeeze Testing, make sure that the PPA has an entry for Ubuntu 10.04 Lucid Lynx. Not that it will never work with Maverick PPAs, but Lucid is a better choice as Debian Squeeze has package versions more similar to Lucid than Maverick or Natty. Thus, it is a better choice to use Lucid PPAs. Instead of using just the PPA name (for example ppa:tiheum/equinox for [Equinox theme PPA](https://launchpad.net/~tiheum/+archive/equinox)) use the deb line for Lucid (eg. deb http://ppa.launchpad.net/tiheum/equinox/ubuntu lucid main ) and add it to /etc/apt/sources.list or Software Sources (or Synaptic>Settings>Repositories>Third Party Source). After adding that, copy the PPA signature (available in "Signing Key" section in PPA page), eg. 1024R/4631BBEA for [Equinox Theme PPA](https://launchpad.net/~tiheum/+archive/equinox). Just use the part after "/" (i.e. 4631BBEA for this example) and use the following command in the terminal to get GPG keys for the PPA:

sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 4631BBEA

Note: If you are not able to sudo, you may [either enable it](http://www.khattam.info/howto-enable-ubuntu-like-sudo-in-debian-squeeze-2010-11-14.html) or use su followed by commands instead. After that, reload the package list and install the package.

This may not work for every program that there is but it works for many. Hope this helps.
