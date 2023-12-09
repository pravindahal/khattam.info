---
title: "Play I-Doser DRG Files on Linux with Freedoser"
date: "2009-04-26"
categories: 
  - "ubuntu-linux"
tags: 
  - "drg"
  - "freedoser"
  - "idoser"
  - "i-doser"
  - "jaunty"
  - "jaunty-jackalope"
  - "linux"
  - "sbagen"
---

I have created I-doser Drug File (.DRG) player for Linux. Have tested this on Ubuntu Jaunty Jackalope 64 Bit but it should work for most Linux distros.

I will illustrate how to install this on Ubuntu. Please follow the instructions carefully to get it working.

**Getting the essentials**  
Make sure you have the universe repository enabled. Then open up the terminal and type in or copy/paste the following commands one after another. Enter password when prompted.

sudo apt-get update
sudo apt-get install build-essential libssl-dev libtool libvorbis-dev libvorbisidec-dev libmad0-dev

**Getting Ready**  
In the terminal, copy\\paste or type in the following commands one after another.

mkdir freedoser
cd freedoser

Move on to the next step with the terminal open.

**Getting the software**  
Download it [here](https://mega.nz/file/cpQWxDRL#o35L2foQ99-UjYqa6rDJkVxy41VNd74tEnGExJJr2vw).

**Unpacking**  
Type in or copy/paste the following command to unpack.

tar -xvvzf freedoser.tar.gz

**Compilation\\Installation**  
Type in the following commands to install. Please report any error you encounter as comments to this blog post. Enter password when prompted.

sudo cp freedoser /usr/bin/
cd drg2sbg
./configure
sed -i 's/-Werror//g' src/Makefile
make
sudo make install
cd ../sbagen-1.4.4/
cp /usr/lib/libvorbisidec.a libs/linux-libvorbisidec.a
cp /usr/lib/libmad.a libs/linux-libmad.a
./mk
sudo cp sbagen /usr/bin/

If you encounter no errors, installation should be complete. Press Alt+F2 to bring up the Run Application dialog and then type in freedoser and press enter. If everything went ok, it should ask you to select a DRG file. Select a DRG you purchased (or received for free) and it will ask you if you want to continue. Press OK and it will start playing. Press Cancel any time to abort.

I have not tested this anywhere else except my PC and it may not work for you. Please post the problems you encounter here and I will see if I can solve it.

I-doser is a trademark of [I-doser.com](http://i-doser.com "I-Doser Labs"). This site/project is not affiliated with [I-Doser Labs](http://i-doser.com "I-Doser Labs") in any way.

Thanks to [Manuel Arguelles](http://code.google.com/u/manuel.arguelles/ "The author of drg2sbg") for porting our code from VB to C. His project page is [here](http://code.google.com/p/drg2sbg/ "drg2sbg project page").  
Thanks to [Jim Peters](http://uazu.net/contact/ "The author of sbagen"), the author of sbagen, who made I-doser possible.

The source code for the freedoser is released under GPL v3 and you may modify/change redistribute it.

Please support the project by recommending I-doser users who use Linux to use try this program in [I-doser forum](http://www.i-doser.com/forum/ "I-Doser Forum").
