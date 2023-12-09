---
title: "[SOLVED] LTSP, \"error: LTSP client installation ended abnormally\""
date: "2010-01-29"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "linux"
  - "ltsp"
  - "ltsp-build-client"
  - "ltsp-server"
  - "lucid"
  - "lucid-lynx"
  - "ubuntu"
---

I wanted to test ltsp in my Ubuntu 10.04 Lucid Lynx and installed ltsp-server-standalone. Then I set up ltsp-client by using

sudo ltsp-build-client

and despite of getting no error messages during installing and configuring, I got this error:

error: LTSP client installation ended abnormally

and it stopped. I searched around and found the solution [here](https://answers.launchpad.net/ubuntu/+question/27500).  
The solution was to use the following set of commands instead of sudo ltsp-build-client

sudo -s
su -
ltsp-build-client

This is probably a bug and hope it is fixed in the newer release.
