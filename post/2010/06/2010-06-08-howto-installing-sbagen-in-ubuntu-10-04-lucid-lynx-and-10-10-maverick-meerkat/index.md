---
title: "[HOWTO] Install sbagen in Ubuntu 10.04 Lucid Lynx and 10.10 Maverick Meerkat"
date: "2010-06-08"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "10-10"
  - "idoser"
  - "linux"
  - "lucid-lynx"
  - "maverick"
  - "maverick-meerkat"
  - "sbagen"
  - "sbg"
---

This guide is outdated. For installing to newer version of sbagen in newer Ubuntu versions, follow instructions [here](http://www.khattam.info/howto-install-sbagen-in-ubuntu-14-04-trusty-tahr-2015-07-21.html).

SBaGen is a Binaural beat generator. For more info, visit the [official SBaGen Website](http://uazu.net/sbagen).

It is available for Linux, Windows and Mac. For Ubuntu, it is not available in any official repos so we need to compile it from source. Here is how you can do that.

Open Synaptic Package Manager and enable universe repository if you already haven't done so. To do so, navigate to Settings > Repositories and check Community-maintained Open Source software (universe) Now, press Reload in Synaptic Toolbar to reload the package lists.

Now, quit Synaptic Package Manager and open up terminal. First, you will need some packages to start building our app. So lets get those.

sudo apt-get install libvorbisidec-dev libmad0-dev

After installing required development packages, lets create a directory named sbagen where you can work with sbagen and change to it.

mkdir sbagen
cd sbagen

Lets download sbagen-1.4.4.tgz from sbagen website:

wget http://uazu.net/sbagen/sbagen-1.4.4.tgz 

Extract it

tar -xvzf sbagen-1.4.4.tgz

and change to that directory

cd sbagen-1.4.4/

Now, lets copy the required files to libs directory

cp /usr/lib/libvorbisidec.a libs/linux-libvorbisidec.a 
cp /usr/lib/libmad.a libs/linux-libmad.a 

Now, to build it, you need to run the included script called mk. To do so, just execute:

./mk

Now if you see no errors, the code must be compiled by now. You should be able to run it by doing a:

./sbagen

If you see an output like the following:

SBaGen - Sequenced Binaural Beat Generator, version 1.4.4
Copyright (c) 1999-2007 Jim Peters, http://uazu.net/, all rights 
  reserved, released under the GNU GPL v2. See file COPYING.

Usage: sbagen \[options\] seq-file ...
       sbagen \[options\] -i tone-specs ...
       sbagen \[options\] -p pre-programmed-sequence-specs ...

For full usage help, type 'sbagen -h'.  For latest version see
http://uazu.net/sbagen/ or http://sbagen.sf.net/

this means sbagen has been compiled. To be able to use it conveniently in the future, you just need to move it to some bin directory. Lets move it to /usr/local/bin

sudo cp sbagen /usr/local/bin/ 

Now, you should be able to run it from any path by just invoking:

sbagen

If you encounter any errors in any steps, please post the step and the corresponding error message in the comment box below. I will try to address the problem the best I can.

Now, after it is installed, you may want to try out an example file:

sbagen examples/basics/prog-chakras-1.sbg 

but it will give you the following error:

Can't open /dev/dsp, errno X

Please follow [my other post](http://www.khattam.info/2010/06/09/solved-cant-open-devdsp-in-ubuntu-10-10-maverick-meerkat/) to overcome this problem.
