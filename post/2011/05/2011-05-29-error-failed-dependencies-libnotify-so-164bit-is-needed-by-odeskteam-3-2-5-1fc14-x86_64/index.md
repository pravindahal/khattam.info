---
title: "[SOLVED] \"error: Failed dependencies: libnotify.so.1()(64bit) is needed by odeskteam-3.2.5-1fc14.x86_64\" while installing odeskteam in Fedora 15"
date: "2011-05-29"
tags: 
  - "fedora"
  - "libnotify"
  - "linux"
  - "odesk"
  - "odeskteam"
  - "odeskteam-qt4"
---

I upgraded to Fedora 15 a few days ago and I wanted to install odeskteam application from oDesk.com by downloading 64-bit RPM. However, I was getting dependency error.

> error: Failed dependencies: libnotify.so.1()(64bit) is needed by odeskteam-3.2.5-1fc14.x86\_64

I checked for "libnotify" in Add/Remove Software and found that it had been installed so I decided to force installation by running:

su
rpm -Uvh /path/to/odeskteam-3.2.5\_fedora\_14\_x86\_64.rpm --nodeps

Then I opened up another terminal instance and tried running it as my user:

odeskteam-qt4

However, I got the following error:

> odeskteam-qt4: error while loading shared libraries: libnotify.so.1: cannot open shared object file: No such file or directory

So, I tried locating the library using locate command:

locate libnotify.so

I found that the following files existed:

/usr/lib64/libnotify.so.4
/usr/lib64/libnotify.so.4.0.0

However, the file "/usr/lib64/libnotify.so.1" was not found. I created a symbolic link for the file using the command:

ln -s /usr/lib64/libnotify.so.4 /usr/lib64/libnotify.so.1

Now, odeskteam-qt4 runs without problems. Note: If you are getting error like this:

> \*\* GLib-GIO:ERROR:gdbusconnection.c:xxxx:initable\_init: assertion failed: (connection->initialization\_error == NULL) \*\* GLib-GIO:ERROR:gdbusconnection.c:xxxx:initable\_init: assertion failed: (connection->initialization\_error == NULL) Resource temporarily unavailable

then, make sure to run odeskteam-qt4 as normal user and not root.
