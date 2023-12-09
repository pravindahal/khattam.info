---
title: "[HOWTO] Change Debian Testing to Linux Mint Debian Edition (LMDE)"
date: "2010-11-26"
categories: 
  - "debian-linux"
  - "lmde"
tags: 
  - "debian"
  - "debian-testing"
  - "linux"
  - "linux-mint"
  - "lmde-2"
---

Linux Mint Debian Edition is a rolling release distro based on Debian Testing. It is currently only available in 32bit and not for other architectures.

If you already have a Debian Testing installation, you will not have problems changing it to Linux Mint, if you wish to. This can be achieved by changing apt sources and preferences and installing Linux Mint meta packages.

Open /etc/apt/sources.list as root and append the following line at the end of the file:

deb http://packages.linuxmint.com/ debian main upstream import

If you want real Linux Mint Debian, you will need to remove other software sources like Unstable repos but have the following at least:

deb http://ftp.debian.org/debian testing main contrib non-free
deb http://security.debian.org/ testing/updates main contrib non-free
deb http://www.debian-multimedia.org testing main non-free

Now, open up /etc/apt/preferences and add the following:

Package: \*
Pin: release o=linuxmint
Pin-Priority: 700

Package: \*
Pin: origin packages.linuxmint.com
Pin-Priority: 700

Package: \*
Pin: release o=Debian
Pin-Priority: 500

The above change will make sure that Linux Mint repos will be favored over Debian.

First upgrade your installation:

apt-get update
apt-get upgrade

Now, install the following packages:

mint-meta-debian
mint-wallpapers-extra
mint-wallpapers-previous-releases

by running:

apt-get install mint-meta-debian mint-wallpapers-extra mint-wallpapers-previous-releases

If some installed packages conflict with the new packages, remove them and try again.

Now, change the default theme to Shiki-wise, remove upper panel and add notification area, mintmenu to lower panel and you are done.
