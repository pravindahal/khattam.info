---
title: "[HOWTO] Install Firefox 4 in Fedora 14"
date: "2010-12-23"
tags: 
  - "fedora"
  - "firefox"
  - "firefox-4"
  - "linux"
  - "spot"
---

Firefox 4 is currently in beta and not available in the Fedora repository. However, it can be installed by adding Spot repository from FedoraPeople. To install, open up the terminal and run the following from terminal as root (to be root, run su and enter root password):

wget http://repos.fedorapeople.org/repos/spot/firefox4/fedora-firefox4.repo -O /etc/yum.repos.d/firefox4.repo
yum install firefox4

When done, Firefox 4 is ready to use.
