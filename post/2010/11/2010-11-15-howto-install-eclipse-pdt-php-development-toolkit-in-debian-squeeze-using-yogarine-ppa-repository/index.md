---
title: "[HOWTO] Install Eclipse-PDT (PHP Development Toolkit) in Debian Squeeze using Yogarine PPA Repository"
date: "2010-11-15"
categories: 
  - "debian-linux"
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "eclipse"
  - "linux"
  - "pdt"
  - "php"
  - "ppa"
---

While you can download the latest version of Eclipse PDT from [Eclipse Download Page](http://www.eclipse.org/pdt/downloads/) and install it manually, it is great to setup a repository instead so that you can get updates from it automatically via update manager. Eclipse is available in the official Debian repos but PDT is not. It is available in [Yogarine Eclipse PPA in Launchpad](https://launchpad.net/~yogarine/+archive/eclipse). For Debian Squeeze, add the following line to Sources.list (or add it via Software Sources or in Third Party Repositories in Synaptic):

deb http://ppa.launchpad.net/yogarine/eclipse/ubuntu lucid main

Then execute the following command as root to add GPG keys:

apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 676DBA91

Now, reload your software list:

apt-get update

Then, install eclipse-pdt:

apt-get install eclipse-pdt

You may not get the latest version, but the repo is constantly updated and easy to manage than to monitor and re-download the same from Eclipse download page and update.
