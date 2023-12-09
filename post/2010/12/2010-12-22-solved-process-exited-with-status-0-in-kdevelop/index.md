---
title: "[SOLVED] \"Process exited with status 0\" in kdevelop"
date: "2010-12-22"
tags: 
  - "fedora"
  - "git"
  - "kdevelop"
  - "linux"
---

I have recently installed KDevelop and was looking for a good editor for programming. I found KDevelop was mentioned in many discussions. So, I decided to give it a try. However, when I ran it, I got the following error:

> Process error - KDevelop Process exited with status 0

However, it did not seem to affect the functionality after closing the dialog, it was quite annoying. I ran it from the terminal and looked for possible error messages, however, I could not find anything. Later, I noticed that the error had magically stopped showing any more. I had installed a few packages after that and I thought that might have solved the problem. After a few hit and trials (of removing the recently installed packages), I found that removing the "git" package brought the error back again.

So, if you are running into similar problems, just install the package git. However, if you do not intend to use git and refuse to install it, you can also disable the plugin by navigating to Settings>Configure KDevelop>Plugins and removing the check mark next to "Git Support".
