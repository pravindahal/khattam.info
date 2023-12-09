---
title: "[HOWTO] Getting Started with J2ME on Ubuntu Karmic Koala with Netbeans"
date: "2009-12-06"
categories: 
  - "ubuntu-linux"
tags: 
  - "9-10"
  - "http-server-is-no-running-start-it-first"
  - "j2me"
  - "jar"
  - "java-mobile-development"
  - "karmic-koala"
  - "linux"
  - "mobile"
  - "mobility"
  - "netbeans"
  - "ubuntu"
  - "ubuntu-9-10"
---

I want to build my college project on J2ME platform. I use Ubuntu and want to use NetBeans as my IDE.

I just installed netbeans, Sun Java Wireless Toolkit for CLDC and Mobility pack for netbeans. Here is how I did it.

I opened up Synaptic and installed netbeans. It installed openjdk as Java Development Kit. You may choose to install sun-java6-jdk instead. It should run fine (maybe better).

Now, when netbeans was installed, I downloaded [Sun Java Wireless Toolkit CLDC from sun website](http://java.sun.com/products/sjwtoolkit/download.html?feed=JSC "Sun Java Wireless Toolkit"). As it has a text based installer, I had to install it via terminal. Opened up the terminal and then changed the directory to where I downloaded the .sh file. Then ran it as sudo sh downloaded\_file\_name.sh. It asks a few questions such as path to JDK etc.

Then, I launched netbeans and then navigated through Tools>Plugins. In the available plugins tab, I just sorted by category and installed both packages (Mobility and Mobile Web) packages.Then I restarted netbeans and then navigated through Tools>Java Platforms. Then I selected Java ME MIDP Emulator and browsed for path where I had installed Sun Java Wireless Toolkit for CLDC.

Then I restarted netbeans again. Now I was able to create J2ME projects. While doing so, I had to select the directory where I installed the Sun Java Wireless Toolkit for CLDC.

I successfully ran the Hello World project inside the emulator.

Thank you for reading. Wish me luck for the project.
