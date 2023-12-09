---
title: "[HOWTO] Setup step debugging PHP in Netbeans on Windows with XAMPP"
date: "2011-04-26"
tags: 
  - "fedora"
  - "netbeans"
  - "php"
  - "php_xdebug-dll"
  - "web"
  - "windows"
  - "xampp"
  - "xdebug"
---

I am using Netbeans 6.9.1 on Windows 7 with XAMPP 1.7.4 installed. I wanted to enable step debugging for PHP like I do in my PC with Fedora (see here for [Netbeans PHP step debugging for Fedora](http://www.khattam.info/howto-configure-netbeans-6-9-to-debug-php-files-using-xdebug-in-fedora-14-2011-02-21.html)). To do that, I had to follow the following steps:

Edit the php.ini file (xampp\\php\\php.ini) in a text editor to uncomment (remove leading semicolon ;) the following lines:

zend\_extension = "D:\\xampp\\php\\ext\\php\_xdebug.dll"
xdebug.remote\_handler = "dbgp"
xdebug.remote\_host = "localhost"
xdebug.remote\_port = 9000

Also, search for the line containing "xdebug.remote\_enable" and change it to:

xdebug.remote\_enable = On

Then restart apache service.

Now, open the file Program Files\\NetBeans 6.9.1\\etc\\netbeans.conf and find the line containing "netbeans\_default\_options". Add the text "-J-Dorg.netbeans.modules.php.dbgp.level=400" at the end of the line so that it looks like the following:

netbeans\_default\_options="-J-client -J-Xss2m -J-Xms32m -J-XX:PermSize=32m -J-XX:MaxPermSize=200m -J-Dapple.laf.useScreenMenuBar=true -J-Dapple.awt.graphics.UseQuartz=true -J-Dsun.java2d.noddraw=true -J-Dorg.netbeans.modules.php.dbgp.level=400"

Now, restart Netbeans and select Debug>Debug Project. However, I have experienced it is very slow on Windows compared to the installation on Fedora.

Hope this helps.
