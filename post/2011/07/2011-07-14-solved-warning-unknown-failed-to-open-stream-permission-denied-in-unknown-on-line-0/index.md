---
title: "[SOLVED] Warning: Unknown: failed to open stream: Permission denied in Unknown on line 0"
date: "2011-07-14"
tags: 
  - "apache"
  - "fedora"
  - "linux"
  - "permissions"
  - "php"
  - "selinux"
---

While trying to run a single-file php script in my Fedora 15 installation, I got a very strange error:

> Warning: Unknown: failed to open stream: Permission denied in Unknown on line 0
> 
> Fatal error: Unknown: Failed opening required '/var/www/html/test/filename.php' (include\_path='.:/usr/share/pear:/usr/share/php') in Unknown on line 0

To get rid of this error, right click and go to Properties. Then, in Permissions, make sure it is readable by other users and it has a SELinux context httpd\_user\_content\_t. That should do it.
