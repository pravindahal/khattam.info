---
title: "[HOWTO] Install sbagen in Ubuntu 14.04 Trusty Tahr"
date: "2015-07-21"
categories: 
  - "trusty-tahr-14-04"
  - "ubuntu-linux"
tags: 
  - "idoser"
  - "linux"
---

SBaGen is a Binaural beat generator. For more info, visit the [official SBaGen Website](http://uazu.net/sbagen).

It is available for Linux, Windows and Mac. For Ubuntu, it is not available in any official repos or ppas so we need to compile it from source. Here is how you can do that.

Make sure you have multiverse repository enabled. You may have it already enabled. Open Software & Sources to check if "Software restricted by copyright or legal issues (multiverse)" is checked.

Then, install the required packages before compiling:

sudo apt-get update
sudo apt-get install libvorbisidec-dev libmad0-dev mlocate -y
sudo updatedb

Download sbagen source code and extract it:

mkdir ~/sbagen
cd ~/sbagen
wget http://uazu.net/sbagen/sbagen-1.4.5.tgz
tar xzvf sbagen-1.4.5.tgz

Compile:

cd ~/sbagen/sbagen-1.4.5
LIBS=$(locate libmad.a | grep /libmad.a)
LIBS="$LIBS $(locate libvorbisidec.a | grep /libvorbisidec.a)"
cc -DMP3\_DECODE -DT\_LINUX -Wall -O3 -s sbagen.c $LIBS -o sbagen.bin -lm -lpthread

If you see no errors, the code must be compiled. You should be able to run it by typing the following:

./sbagen.bin

If you see an output like the following, then it is installed successfully:

SBaGen - Sequenced Binaural Beat Generator, version 1.4.5
Copyright (c) 1999-2011 Jim Peters, http://uazu.net/, all rights 
  reserved, released under the GNU GPL v2. See file COPYING.

Usage: sbagen \[options\] seq-file ...
       sbagen \[options\] -i tone-specs ...
       sbagen \[options\] -p pre-programmed-sequence-specs ...

For full usage help, type 'sbagen -h'.  For latest version see
http://uazu.net/sbagen/ or http://sbagen.sf.net/

If you try to run an sbg file however:

./sbagen.bin examples/basics/prog-chakras-1.sbg

you will most probably receive an error:

Can't open /dev/dsp, errno 2

To fix this, we will run it with OSS emulation using padsp:

padsp ./sbagen.bin examples/basics/prog-chakras-1.sbg

So, we will create a simple wrapper so that it is always run with padsp and install it such that it is available in path:

echo padsp sbagen.bin \\"\\$@\\" > sbagen
chmod +x sbagen
sudo cp sbagen.bin /usr/local/bin/
sudo cp sbagen /usr/local/bin/

Now, you can simply run:

sbagen examples/basics/prog-chakras-1.sbg

Hope it works. Post a comment if you encounter any issues.
