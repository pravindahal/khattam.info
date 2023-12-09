---
title: "[HOWTO] Install SBaGen in Fedora"
date: "2011-05-05"
tags: 
  - "fedora"
  - "linux"
  - "sbagen"
---

I am running Fedora 14 32 bit (and now Fedora 15 64 bit for which I have updated the article) and I wanted to install SBaGen for some binaural entertainment. So, here is how I did it:

### Download

cd
mkdir sbagen
cd sbagen
wget http://uazu.net/sbagen/sbagen-1.4.4.tgz
tar xzvf sbagen-1.4.4.tgz
cd sbagen-1.4.4

### Install dependencies

sudo yum install libmad-devel libvorbis-devel gcc

### Run Build Script

For 32 bit:

./mk

For 64 bit:

wget "https://launchpadlibrarian.net/35151187/libvorbisidec\_1.0.2+svn16259.orig.tar.gz"
tar xzvf "libvorbisidec\_1.0.2+svn16259.orig.tar.gz"
cd "libvorbisidec-1.0.2+svn16259"
./autogen.sh
make
sudo make install
sudo ln -s /usr/local/lib/libvorbisidec.so.1 /usr/lib64/libvorbisidec.so.1
cd ..
cp /usr/lib64/libvorbisidec.so.1 libs/linux-libvorbisidec.a
cp /usr/lib64/libmad.so libs/linux-libmad.a
./mk

That should build a sbagen executable in the same directory. Run the following to verify:

./sbagen

It should output something like this:

> SBaGen - Sequenced Binaural Beat Generator, version 1.4.4 Copyright (c) 1999-2007 Jim Peters, http://uazu.net/, all rights reserved, released under the GNU GPL v2. See file COPYING.
> 
> Usage: sbagen \[options\] seq-file ... sbagen \[options\] -i tone-specs ... sbagen \[options\] -p pre-programmed-sequence-specs ...
> 
> For full usage help, type 'sbagen -h'. For latest version see http://uazu.net/sbagen/ or http://sbagen.sf.net/

Now, copy it to /usr/bin/ and thats all.

sudo cp sbagen /usr/bin/

Now, you must be able to run it. Try running an example:

sbagen examples/basics/prog-chakras-1.sbg

If you get something along the lines of:

> Can't open /dev/dsp, errno X

You will need to prefix the command by padsp like this:

padsp sbagen examples/basics/prog-chakras-1.sbg

Hope this helps.
