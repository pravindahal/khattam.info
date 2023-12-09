---
title: "[HOWTO] Open djvu files in Fedora 15"
date: "2011-06-09"
tags: 
  - "djview"
  - "djvu"
  - "evince"
  - "fedora"
  - "linux"
---

Support for djvu files is not included in Fedora default installation, however, it can be installed from the repository. To add djvu support to the default document viewer (Evince) run the following in terminal:

su -c 'yum install evince-djvu'

If you want to install a different reader for djvu files, you can do so by installing djview. To install djview, type in the following in terminal.

su -c 'yum install djview4'

Hope this helps.
