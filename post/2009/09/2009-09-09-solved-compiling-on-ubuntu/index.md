---
title: "[SOLVED] cmake error when compiling plasmoid on Ubuntu"
date: "2009-09-09"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "compiling"
  - "error"
  - "karmic"
  - "kubuntu"
  - "linux"
  - "plasmoid"
  - "ubuntu"
  - "yet-another-weather-plasmoid"
---

I have recently installed kubuntu-desktop (KDE4) on my Karmic Koala installation and tried to install a very cool weather plasmoid called [Yet Another Weather Plasmoid](http://www.kde-look.org/content/show.php/yaWP+%28Yet+Another+Weather+Plasmoid%29?content=94106 "Yet Another Weather Plasmoid") but I was unable to do so as I got this error: ``CMake Error at /usr/share/cmake-2.6/Modules/FindKDE4.cmake:84 (MESSAGE): ERROR: cmake/modules/FindKDE4Internal.cmake not found in /home/pravin/.kde/share/apps;/usr/share/kubuntu-default-settings/kde4-profile/default/share/apps;/usr/share/kde4/apps Call Stack (most recent call first): CMakeLists.txt:3 (find_package)  CMake Warning (dev) in CMakeLists.txt: No cmake_minimum_required command is present. A line of code such as  cmake_minimum_required(VERSION 2.6)  should be added at the top of the file. The version specified may be lower if you wish to support older CMake versions for this project. For more information run "cmake --help-policy CMP0000". This warning is for project developers. Use -Wno-dev to suppress it.  -- Configuring incomplete, errors occurred! make: *** No rule to make target `clean'. Stop. make: *** No targets specified and no makefile found. Stop. Compilation failed, sorry :-(``

I installed kdelibs5-dev and I was able to compile it.

Hope this helps.
