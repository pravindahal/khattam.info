---
title: "[HOWTO] Install Limewire in Ubuntu 10.04 Lucid Lynx or 10.10 Maverick Meerkat"
date: "2010-08-14"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "dpkg-deb"
  - "kubuntu"
  - "limewire"
  - "linux"
  - "nano"
---

Limewire is a P2P file sharing application available for Linux, Windows and Mac OS X. It can be downloaded from [Official Limewire Website](http://www.limewire.com/) or [Click here for Direct Download](http://www.limewire.com/LimeWireSoftLinuxDeb). After downloading it, if you double click it (LimeWireLinux.deb), you may get the following error:

> Error: Dependency is not satisfiable: sun-java6-jre|icedtea-java7-jre|sun-java6-jdk|icedtea-java7-jdk

This can be solved by either adding/enabling the Lucid Partner Repository for sun-java6-jre or by modifying LimeWireLinux.deb to be satisfied with openjdk-6-jre. **Method 1: Making sun-java6-jre available** sun-java6-jre is not available in the maverick partner repository at the time of writing this and for now, using Lucid Partner Repository works in Maverick too. To enable it:

**Using Terminal:** Run the following:

sudo  add-apt-repository "deb http://archive.canonical.com/ lucid partner"
sudo apt-get update

**Using Synaptic:** just launch Synaptic Package Manager (System>Administration) and then click on other software and add the following:

deb http://archive.canonical.com/ lucid partner

and then close the Repositories window. Now, Reload and then close Synaptic.

Now, double click LimeWireLinux.deb. Now you should be able to install it. **Method 2: Modifying LimeWireLinux.deb**

However, if you don't want to use sun-java6-jre, you can modify LimeWireLinux.deb to use OpenJRE instead of sun-java6-jre. To do so, install dpkg-repack by running the following command in the terminal:

sudo apt-get install dpkg-repack

Now, change directory to where your LimeWireLinux.deb is situated and then run the following command:

mkdir -p extract/DEBIAN
dpkg-deb -x LimeWireLinux.deb extract/
dpkg-deb -e LimeWireLinux.deb extract/DEBIAN/
cd extract/DEBIAN

Now, you will need to edit the control file. To do so, open it in your text editor. In Ubuntu, you can use gedit

gedit control

In Kubuntu, you might use kate:

kate control

Or you might just use nano:

nano control

Now, find the line:

Depends: debconf, sun-java6-jre | icedtea-java7-jre | sun-java6-jdk | icedtea-java7-jdk

and change it to:

Depends: debconf, openjdk-6-jre | sun-java6-jre | icedtea-java7-jre | sun-java6-jdk | icedtea-java7-jdk

by adding “openjdk-6-jre | “.

When done, save and close the text editor and run the following set of commands to repack it:

cd ../../
mkdir build
dpkg-deb -b extract/ build/

Now, you should find limewire-basic\_X\_all.deb (X being the version) in the build directory. Just double click on it and install.

Hope this helps.
