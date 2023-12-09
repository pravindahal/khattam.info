---
title: "[SOLVED] \"Error: Dependency is not satisfiable: libnautilus-extension1 (&gt;= 1:2.22.2)\" while installing dropbox"
date: "2010-11-27"
categories: 
  - "debian-linux"
  - "ubuntu-linux"
tags: 
  - "deb"
  - "dropbox"
  - "linux"
---

I downloaded nautilux-dropbox Ubuntu deb package from [Dropbox Linux Download Page](https://www.dropbox.com/downloading?os=lnx). When I tried to install it via gdebi deb installer in Debian, I got the following error:

> Error: Dependency is not satisfiable: libnautilus-extension1 (>= 1:2.22.2)

If you add repos and try to install it from there via Synaptic, you will get the error:

> nautilus-dropbox: Depends: libnautilus-extension1 (>=1:2.22.2) but 2.30.1-2 is to be installed

If you install it with dpkg -i, you will get the following error:

> Selecting previously deselected package nautilus-dropbox. (Reading database ... 229404 files and directories currently installed.) Unpacking nautilus-dropbox (from nautilus-dropbox\_0.6.7\_i386.deb) ... dpkg: dependency problems prevent configuration of nautilus-dropbox: nautilus-dropbox depends on libnautilus-extension1 (>= 1:2.22.2); however: Version of libnautilus-extension1 on system is 2.30.1-2. dpkg: error processing nautilus-dropbox (--install): dependency problems - leaving unconfigured Processing triggers for gnome-menus ... Processing triggers for desktop-file-utils ... Processing triggers for hicolor-icon-theme ... Processing triggers for man-db ... Errors were encountered while processing: nautilus-dropbox

Using the dpkg method will result in broken packages.

I had downloaded the version 0.6.7 32 bit (i386) i.e. nautilus-dropbox\_0.6.7\_i386.deb and was unable to install it cleanly. However, when I ran it by force installing, it ran without problems but the package was broken. So, the problem was not with the unmet dependencies but the deb file wrongly specifying dependencies.

So, I decided to fix the deb file. I unpacked the deb:

mkdir -p extract/DEBIAN
dpkg-deb -x nautilus-dropbox\_0.6.7\_i386.deb extract/
dpkg-deb -e nautilus-dropbox\_0.6.7\_i386.deb extract/DEBIAN/

Then edited the extract/DEBIAN/control file with gedit. You can use any other text editor of your choice. The "Depends:" line looks like the following:

Depends: libatk1.0-0 (>= 1.20.0), libc6 (>= 2.4), libcairo2 (>= 1.6.0), libglib2.0-0 (>= 2.16.0), libgtk2.0-0 (>= 2.12.0), libnautilus-extension1 (>= 1:2.22.2), libpango1.0-0 (>= 1.20.1), python (>= 2.5), python-gtk2 (>= 2.12)

Notice the entry "libnautilus-extension1 (>= 1:2.22.2)". In my installation, the version of libnautilus-extension1 is 2.30.1 and not 1:2.30.1 (which is the version format for libnautilus-extension1 in Ubuntu). So, I edited the version number to 2.22.2 instead of 1:2.22.2. So, the new depends line looks like the following:

Depends: libatk1.0-0 (>= 1.20.0), libc6 (>= 2.4), libcairo2 (>= 1.6.0), libglib2.0-0 (>= 2.16.0), libgtk2.0-0 (>= 2.12.0), libnautilus-extension1 (>= 2.22.2), libpango1.0-0 (>= 1.20.1), python (>= 2.5), python-gtk2 (>= 2.12)

After the change, create a directory called build and run the dpkg-deb command with -b switch to build the new deb file:

mkdir build
dpkg-deb -b extract/ build/

You will find a deb file in build/ directory which should install without dependency problems.

After installing, install the service by running the following as root and you are all done:

dropbox start -i

Hope this helps.
