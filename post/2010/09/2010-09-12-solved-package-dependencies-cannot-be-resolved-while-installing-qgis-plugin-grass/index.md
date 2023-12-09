---
title: "[SOLVED] \"Package dependencies cannot be resolved\" while installing qgis-plugin-grass"
date: "2010-09-12"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "dpkg-deb"
  - "grass"
  - "linux"
  - "package"
  - "qgis-plugin-grass"
  - "quantum-gis"
  - "software-center"
  - "synaptic"
---

I was trying to install GRASS Plugin for Quantum GIS (qgis-plugin-grass) in my Ubuntu 10.10 Maverick Meerkat while I got the following error in Ubuntu Software Center:

> **Package dependencies cannot be resolved** This error could be caused by required additional software packages which are missing or not installable. Furthermore there could be a conflict between software packages which are not allowed to be installed at the same time.

I then launched Synaptic Package Manager (from System>Administration menu) and tried to install qgis-plugin grass and got the following error message:

> qgis-plugin-grass: Depends: libgdal1-1.6.0-grass but it is not going to be installed

I then tried to install libgdal1-1.6.0-grass which gave me the following error:

> libgdal1-1.6.0-grass: Depends: grass640-6 but it is not installable

I looked for grass640-6 package but it was not available. However, a package named grass was available which was at version number 6.0.4-rc6 was available. I decided to make a new dummy transitional package (which the developers should have done). To do so, I just created a directory grass640 with another directory DEBIAN and created a file control inside it:

mkdir -p grass640/DEBIAN
touch grass640/DEBIAN/control

Then, I opened up control file that I just created in gedit:

gedit grass640/DEBIAN/control

and wrote the following content and saved it:

Package: grass640-6
Source: grass
Version: 0.6.4.0-6
Architecture: all
Maintainer: khattam@khattam.info
Installed-Size: 0
Depends: grass
Priority: extra
Homepage: http://www.khattam.info
Description: transitional dummy package for grass
 transitional dummy package to pull in grass

Then, I built the debain file:

dpkg-deb -b grass640/ ./

As a result, I got a file named grass640-6\_0.6.4.0-6\_all.deb in my current directory. If you don't want to create it, you can use mine from [here](https://mega.nz/file/p4YGCBrb#vK9fJsrrT1zZcJUCrJzzj8SEtoZMvjRFAjaPs9NLALs). Then I just installed it by double clicking on it. After that, I could install qgis-plugin-grass without problems.

Hope this helps.
