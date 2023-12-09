---
title: "[HOWTO] Run HTML files as PHP in Hostgator"
date: "2010-08-18"
tags: 
  - "hostgator"
  - "htaccess"
  - "web"
---

I recently moved some of my websites to Hostgator shared hosting. One of my sites required html files to be run as PHP. The HTML files contained PHP code which needed to be executed. The site was added as an Addon Domain in Hostgator. That can be done in most hosts by creating a .htaccess host in the root directory of the website (The root directory of the website is something like /pubic\_html/yoursite.com/ in cpanel, by default) and adding the following line to it:

AddHandler application/x-httpd-php .html

. The same can also be achieved by adding the following to .htaccess:

    SetHandler application/x-httpd-php

But in hostgator, none of those will work. You will need to write x-httpd-php5 instead of x-httpd-php i.e.

AddHandler application/x-httpd-php5 .html

If you wish to add other extensions, lets say .htm too for example, you can simply put in:

AddHandler application/x-httpd-php5 .html .htm
