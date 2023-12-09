---
title: "[HOWTO] Install Skype in Fedora 15 64 bit"
date: "2011-06-01"
tags: 
  - "32-bit"
  - "64-bit"
  - "fedora"
  - "linux"
  - "skype"
---

Skype is available as rpm package for Fedora 13+ from [here](http://www.skype.com/go/getskype-linux-beta-fc10) and it installs successfully on 64 bit installations as well, however, it does not run. If you run it from the terminal, you will see the following error:

> skype: error while loading shared libraries: libXv.so.1: cannot open shared object file: No such file or directory

**UPDATE:** A system update has changed a few things and this guide has been updated. So, please update your system first by running the following in your terminal:

su -c 'yum update'

For this to run, the 32 bit versions of libraries it depends on must be installed after installing the rpm. To be able to do so, first of all, open the file /etc/rpm/macros as root and add the following line at the end of the file (the file may be empty or may not exist if you haven't made changes to it or created it already, in that case, just create the file and put the following line in the beginning):

%\_query\_all\_fmt %%{name}-%%{version}-%%{release}.%%{arch}

Save the file and exit the editor. To open as root and add the line, I used nano (you may need to [enable sudo](http://www.khattam.info/howto-enable-sudo-in-fedora-15-2011-05-31.html) first):

su -c 'nano /etc/rpm/macros'

You can press Ctrl+O followed by to write into the file and Ctrl+X to exit nano.

After having done that, you will need to install 32-bit libraries that are required by skype. The following command installs them all:

su -c 'yum install qt.i686 qt-x11.i686 libXv.i686 libXScrnSaver.i686'

After that, Skype should run without problems. Hope this helps.
