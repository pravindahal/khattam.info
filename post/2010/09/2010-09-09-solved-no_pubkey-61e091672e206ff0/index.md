---
title: "[SOLVED] NO_PUBKEY 61E091672E206FF0"
date: "2010-09-09"
categories: 
  - "maverick-ubuntu-linux-linux"
tags: 
  - "61e091672e206ff0"
  - "linux"
  - "no_pubkey"
---

Running this commands in the terminal will stop these messages:

gpg --keyserver keyserver.ubuntu.com --recv 61E091672E206FF0
gpg --export --armor 61E091672E206FF0 | sudo apt-key add -

Done.
