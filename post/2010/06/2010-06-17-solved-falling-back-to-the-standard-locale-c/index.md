---
title: "[SOLVED] Falling back to the standard locale (\"C\")."
date: "2010-06-17"
categories: 
  - "hardy-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "8-04"
  - "linux"
  - "locale"
  - "locales"
  - "ubuntu"
---

In Ubuntu 8.04 Server, I was getting these messages every now and then:

perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
	LANGUAGE = (unset),
	LC\_ALL = (unset),
	LANG = "en\_US.utf8"
    are supported and installed on your system.
perl: warning: Falling back to the standard locale ("C").
locale: Cannot set LC\_CTYPE to default locale: No such file or directory
locale: Cannot set LC\_MESSAGES to default locale: No such file or directory
locale: Cannot set LC\_ALL to default locale: No such file or directory

To solve this, I just had to install language pack:

apt-get install language-pack-en-base

If this does not solve the problem, you may as well try:

dpkg-reconfigure locales

Hope this helps.
