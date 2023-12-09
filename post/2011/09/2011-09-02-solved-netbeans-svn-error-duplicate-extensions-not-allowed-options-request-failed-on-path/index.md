---
title: "[SOLVED] Netbeans svn error \"Duplicate extensions not allowed, OPTIONS request failed on 'path'\""
date: "2011-09-02"
categories: 
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "fedora"
  - "java"
  - "linux"
  - "netbeans"
  - "subversion"
  - "svn"
---

I have installed sun-java-jre/jdk on my Ubuntu and Fedora. I am using svn for my project and have been running it well with my old Fedora 15 installation on my old PC. However, recently I installed Fedora on my other machine and installed Netbeans 7.0.1 on top of sun-java. Fedora did not handle graphics very well, so I installed Ubuntu alongside as well. But every time I tried to access subversion functionality from Netbeans, I got the following error:

> org.tigris.subversion.javahl.ClientException: java.io.IOException: Duplicate extensions not allowed OPTIONS request failed on '/relative/path/to/some/project/directory'

This happened in both of my newer installations, Fedora 15 and Ubuntu 11.04, both with Netbeans 7.0.1. I tried several things but all in vain. Finally, when searching for installed Java related packages in my old machine (where subversion always worked), I found the required package. The cryptic error message will simply stop appearing and Netbeans subversion will start working after the installation of svn client adapter for Netbeans. Here is how you can do it from the terminal:

For Fedora:

su -c 'yum install netbeans-svnclientadapter'

For Ubuntu:

sudo apt-get install libnb-svnclientadapter-java

Hope this helps.
