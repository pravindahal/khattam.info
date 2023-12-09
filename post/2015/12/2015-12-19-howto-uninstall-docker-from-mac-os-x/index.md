---
title: "[HOWTO] Uninstall docker from Mac OS X"
date: "2015-12-19"
categories: 
  - "mac"
tags: 
  - "docker"
---

So, you have installed docker using the official installer in your OS X and don't want to use it anymore for some reason. Here is how you can get rid of it completely. Open a terminal and run the following commands:

cd /tmp
wget https://raw.githubusercontent.com/docker/toolbox/master/osx/uninstall.sh
chmod +x uninstall.sh
sudo ./uninstall.sh
rm ./uninstall.sh
