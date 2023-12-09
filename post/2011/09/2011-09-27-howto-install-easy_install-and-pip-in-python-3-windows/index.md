---
title: "[HOWTO] Install easy_install and pip in Python 3 (Windows)"
date: "2011-09-27"
tags: 
  - "easy_install"
  - "pip"
  - "python"
  - "python3"
  - "windows"
---

I am just starting with Python 3 on Windows and I wanted to install easy\_install and/or pip for installing other available packages easily. However, I found that setuptools setup for Python 3.3.2 (the version I am using) is not available.

I discovered distribute, a fork of setuptools, which provides easy\_install. I downloaded source from [Python Package page for distribute](http://pypi.python.org/pypi/distribute#downloads) and extracted it. In the elevated command prompt (cmd->Run as Administrator), I changed to extracted directory and then ran distribute\_setup.py. Then, easy\_install was successfully installed in Python\_Directory\\Scripts. Then, I could install pip by changing directory to Scripts and running the following:

easy\_install pip

Hope this helps.
