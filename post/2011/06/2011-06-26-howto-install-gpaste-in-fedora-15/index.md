---
title: "[HOWTO] Install GPaste in Fedora 15"
date: "2011-06-26"
tags: 
  - "fedora"
  - "gnome-3"
  - "gpaste"
  - "linux"
---

GPaste is a clipboard management tool for GNOME 3. It is not available in the repos and must be downloaded via git and compiled. Here is how you can do it:

UPDATE: GPaste is now available in the repos, so you can install it by using Add/Remove Programs or by running the following commands in the terminal:

su
yum install gpaste

That should install GPaste. The following post is for historical reasons only.

**Install Git**

su -c 'yum install git'

**Download GPaste sources**

cd; git clone https://github.com/Keruspe/GPaste.git

**Install Dependencies**

su -c 'yum install gtk3-devel glib2-devel intltool automake autoconf vala'

**Compile and Install**

cd;cd GPaste
./autogen.bash
./configure --prefix=/usr
make
su -c 'make install'

**Restart GNOME Shell** To restart, press Alt+F2, enter 'r' (without quotes) and press enter.

You should now see GPaste icon in the top panel.
