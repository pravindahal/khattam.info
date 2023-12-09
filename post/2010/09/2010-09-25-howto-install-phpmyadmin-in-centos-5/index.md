---
title: "[HOWTO] Install phpMyAdmin in CentOS 5"
date: "2010-09-25"
categories: 
  - "centos-rhel"
tags: 
  - "linux"
  - "mysql"
  - "phpmyadmin"
  - "rpmforge"
  - "yum"
---

I am using CentOS 5 in one of my Virtual Servers and I wanted it to have phpMyAdmin. I tried installing it by doing yum install phpmyadmin but it said No package phpmyadmin available. So I add to add a repo. I discovered that [rpmforge repo](http://rpmrepo.org/RPMforge) had this package. To add it, I executed the following commands:

wget http://packages.sw.be/rpmforge-release/rpmforge-release-0.5.1-1.el5.rf.i386.rpm
rpm -Uhv rpmforge-release-0.5.1-1.el5.rf.i386.rpm

If you have 64-bit version installed, you should try this one out:

wget http://packages.sw.be/rpmforge-release/rpmforge-release-0.5.1-1.el5.rf.x86\_64.rpm
rpm -Uhv rpmforge-release-0.5.1-1.el5.rf.x86\_64.rpm

If you get a 404 Not Found, then you will need to figure out the latest updated version of repo url from [rpmforge usage page](http://rpmrepo.org/RPMforge/Using).

After that, you may like to update your packages by doing this:

yum update

and then continue installing phpmyadmin

yum install phpmyadmin

It should ask you for confirmation and you can continue installing phpMyAdmin with dependencies.

When installation is done, you can edit /etc/httpd/conf.d/phpmyadmin.conf and allow it to be opened from anywhere and not just the same computer. You are going to need this if you have installed it in a remote virtual server. To do so, open up /etc/httpd/conf.d/phpmyadmin.conf using:

nano /etc/httpd/conf.d/phpmyadmin.conf

You will see:

  Order Deny,Allow
  Deny from all
  Allow from 127.0.0.1

Just change the line "Allow from 127.0.0.1" to "Allow from \[yourip\]", where \[yourip\] is IP address of your computer if you have public static IP. Otherwise, you can also set it to "Allow from all". Press Ctrl+O followed by Enter to save and Ctrl+X to exit nano.

Now, you must restart apache. To do so, run

service httpd restart

Now, you can access phpMyAdmin by visiting http://vps\_server\_IP\_or\_domain/phpmyadmin. But you will get the following error:

> **Error** The configuration file now needs a secret passphrase (blowfish\_secret).

To make it work, you will need to edit config.inc.php. To do so, type in:

nano /usr/share/phpmyadmin/config.inc.php

Find a line saying:

$cfg\['blowfish\_secret'\] = ''; /\* YOU MUST FILL IN THIS
FOR
COOKIE AUTH! \*/

Fill in any secret keyword there, eg mysecretpassphrase, so that it looks like:

$cfg\['blowfish\_secret'\] = 'mysecretpassphrase'; /\* YOU MUST FILL IN THIS
FOR
COOKIE AUTH! \*/

and then save it.

If you don't have mysql server installed, you will get the following error:

> Error #2002 - The server is not responding (or the local MySQL server's socket is not correctly configured)

To install mysql-server, just run:

 yum install mysql-server

and then start it:

 service mysqld start

Then change the root password:

mysqladmin -u root password PASSWORD\_HERE

Now, you will have to remove phpmyadmin:

yum remove phpmyadmin

and reinstall it again:

yum install phpmyadmin

Then you will need to edit the config.inc.php again to enter blowfish secret (see above). Then, you can login.

If however, you want phpMyAdmin to connect to a remote server, you can change the line by replacing localhost with your server IP:

$cfg\['Servers'\]\[$i\]\['host'\] = 'localhost';

Hope this helps.
