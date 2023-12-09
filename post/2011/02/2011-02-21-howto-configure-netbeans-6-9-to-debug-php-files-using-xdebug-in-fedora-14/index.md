---
title: "[HOWTO] Configure Netbeans 6.9 to debug PHP files using xdebug in Fedora 14"
date: "2011-02-21"
tags: 
  - "fedora"
  - "fedora-14"
  - "linux"
  - "netbeans"
  - "php"
  - "web"
  - "xdebug"
---

I am using Netbeans 6.9 on Fedora 14 for Web development. I have enabled PHP debugging for making PHP development easier. Here is how you can do it too.

### Install and enable xdebug

Use yum to install php-pecl-xdebug:

sudo yum install php-pecl-xdebug

Now, open the file /etc/php.d/xdebug.ini in a text editor as root. I use nano:

sudo nano /etc/php.d/xdebug.ini 

Now , make sure the following options are set enabled in ini:

; Enable xdebug extension module
zend\_extension=/usr/lib/php/modules/xdebug.so
xdebug.remote\_enable=on
xdebug.remote\_handler=dbgp
xdebug.remote\_host=localhost
xdebug.remote\_port=9000

### Allow port for xdebug

sudo semanage port -a -t http\_port\_t -p tcp 9000 

### Restart Apache:

sudo service httpd restart

### Configure Netbeans to use PHP debugger

Now, open up the file /usr/share/netbeans/6.9/etc/netbeans.conf in a text editor and add the text "-J-Dorg.netbeans.modules.php.dbgp.level=400" in netbeans\_default\_options so that the line looks somewhat like this:

netbeans\_default\_options="-J-client -J-Xss2m -J-Xms32m -J-XX:PermSize=32m -J-XX:MaxPermSize=200m -J-Dapple.laf.useScreenMenuBar=true -J-Dsun.java2d.noddraw=true -J-Dorg.netbeans.modules.php.dbgp.level=400"

Restart netbeans and given that you have configured the project directories properly, you should be able to click on the debug button and start debugging PHP file.
