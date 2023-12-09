---
title: "[SOLVED] How to fix the error \"locale: Cannot set LC_CTYPE to default locale: No such file or directory\" when \"ssh\"ing from Mac OS X"
date: "2015-11-12"
categories: 
  - "mac"
tags: 
  - "linux"
---

This happens because ssh sends a LANG environment variable. If we configure ssh to stop sending the variable, the error should be fixed.

sudo nano /etc/ssh/ssh\_config

Look for line:

   SendEnv LANG LC\_\*

And uncomment it so that it looks like:

\#   SendEnv LANG LC\_\*

If you still see the error, generate the locales on the machine you are connecting to, which looks like the following:

sudo locale-gen en\_US en\_US.UTF-8
sudo dpkg-reconfigure locales
