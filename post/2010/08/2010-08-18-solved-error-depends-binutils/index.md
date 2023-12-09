---
title: "[SOLVED] ERROR: Depends: binutils ("
date: "2010-08-18"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "0ad"
  - "binutils"
  - "getdeb"
  - "linux"
  - "playdeb"
  - "synaptic"
---

I am using Ubuntu 10.10 Maverick Meerkat and have getdeb (playdeb) repository for Lucid Lynx. Lucid repo can be added to Maverick and many applications can be installed without problems. However, I got this error while trying to install a game called 0ad.

> 0ad: Depends: binutils (<2.20.2) but 2.20.51.20100710-1ubuntu2 is to be installed

I could downgrade my binutils to an appropriate version by downloading deb from somewhere else and that would be the ideal thing to do if it did not break any packages, but I decided not to as it could break other packages and decided to try out something that is never recommended and should not be done if you don’t know what you are doing. You should know that this could also lead to broken packages but fortunately this only breaks a game (that is what I am going to install) at worst and not some system program. I just changed the dependency to the version that I had by editing the package description. To do so, I needed to open the file /var/lib/apt/lists/archive.getdeb.net\_ubuntu\_dists\_lucid-getdeb\_games\_binary-amd64\_Packages as root by running

gksu gedit /var/lib/apt/lists/archive.getdeb.net\_ubuntu\_dists\_lucid-getdeb\_games\_binary-amd64\_Packages

If you are using 32-bit version of Ubuntu, you should probably try something else.

The package description for 0ad looks like the following:

Package: 0ad
Version: 0.0.0+r07539~pre-alpha-1~getdeb1
Architecture: amd64
Maintainer: Christoph Korn
Installed-Size: 10412
Depends: binutils (>= 2.20.1-3ubuntu2), binutils (<< 2.20.52), libboost-filesystem1.40.0 (>= 1.40.0-1), libboost-signals1.40.0 (>= 1.40.0-1), libboost-system1.40.0 (>= 1.40.0-1), libc6 (>= 2.11), libdevil1c2, libenet0debian1, libgamin0 | libfam0, libgcc1 (>= 1:4.1.1), libgl1-mesa-glx | libgl1, libglu1-mesa | libglu1, libjpeg62, libopenal1, libpng12-0 (>= 1.2.13-4), libsdl1.2debian (>= 1.2.10-1), libstdc++6 (>= 4.4.0), libvorbisfile3 (>= 1.1.2), libwxbase2.8-0 (>= 2.8.10.1), libwxgtk2.8-0 (>= 2.8.10.1), libx11-6 (>= 0), libxml2 (>= 2.7.4), zlib1g (>= 1:1.2.0), 0ad-data
Homepage: http://wildfiregames.com/0ad/
Priority: normal
Section: games
Filename: pool/games/0/0ad/0ad\_0.0.0+r07539~pre-alpha-1~getdeb1\_amd64.deb
Size: 3835504
SHA256: d21eea643c4fc6cef6564f1eacbc1bf3a2ef7ca813cbb9cc69912e45ae7708a4
SHA1: 504cdbc3fb2acc6ab4a57ab3bddb652a05910f3d
MD5sum: 8dfced6b1af656f5ff820861e621f393
Description: A war/economy strategy game
A historically based Real Time Strategy game focusing
on the years 500 B.C. to 500 A.D.
.
In short, it is a war/economy strategy game allowing
you to recreate or rewrite the ancient history of western
civilisations.

I changed the line in the “Depends” from binutils (<< 2.20.2) to binutils (<< 2.20.52) and restarted synaptic package manager. Then I could download the game without problems. But it shows dependency errors and the game can’t be configured. So, I removed it from Synaptic. Then what I do next is copy the 0ad deb file to my desktop; mine is called 0ad\_0.0.0+r07539~pre-alpha-1~getdeb1\_amd64.deb and it is in /var/cache/apt/archives/. So, I fire up the terminal and do the following:

sudo cp /var/cache/apt/archives/0ad\_0.0.0+r07539~pre-alpha-1~getdeb1\_amd64.deb /home/\[USERNAME\]/Desktop/

where \[USERNAME\] is my username. Now the game is copied onto my desktop. Now I changed the owner to myself, so that I can read it:

sudo chown \[USERNAME\] /home/\[USERNAME\]/Desktop/0ad\_0.0.0+r07539~pre-alpha-1~getdeb1\_amd64.deb

Then, I needed to edit the control file and repack the deb. To do so, I just extracted it:

cd ~/Desktop
mkdir -p extract/DEBIAN
dpkg-deb -x 0ad\_0.0.0+r07539~pre-alpha-1~getdeb1\_amd64.deb extract/
dpkg-deb -e 0ad\_0.0.0+r07539~pre-alpha-1~getdeb1\_amd64.deb extract/DEBIAN/

Then, I edited the control file:

cd extract/DEBIAN
nano control

and changed the file to say binutils (<< 2.20.52) instead of binutils (<< 2.20.2). Just Ctrl+O followed by ENTER to write the changes and Ctrx+X to exit nano. Then, I just went back to the Desktop folder.

cd ../../

Then I repackaged the deb file:

mkdir build
 dpkg-deb -b extract/ build/

Then, I could find the new deb inside the build folder in the Desktop which I can install without problems. After it is installed, I tried to launch it from the terminal (0ad) but I got an error saying:

> ./pyrogenesis: error while loading shared libraries: libbfd-2.20.1-system.20100303.so: cannot open shared object file: No such file or directory

So, it really needs the binutils version it says it does. Anyways, just creating a symbolic link named libbfd-2.20.1-system.20100303.so in /usr/lib to the version that I have i.e. libbfd-2.20.1-system.20100303.so did it for me. To do so, in terminal I typed the following:

sudo ln -s /usr/lib/libbfd-2.20.51-system.20100710.so /usr/lib/libbfd-2.20.1-system.20100303.so

Hope this helps.
