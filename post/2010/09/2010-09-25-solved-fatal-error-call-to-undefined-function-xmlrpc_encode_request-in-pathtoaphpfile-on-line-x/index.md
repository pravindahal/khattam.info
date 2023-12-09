---
title: "[SOLVED] Fatal error: Call to undefined function xmlrpc_encode_request() in /path/to/a/php/file on line x"
date: "2010-09-25"
categories: 
  - "centos-rhel"
  - "ubuntu-linux"
tags: 
  - "apache"
  - "apt-get"
  - "linux"
  - "php"
  - "xmlrpc"
  - "yum"
---

I was trying to use xmlrpc\_encode\_request() for posting to wordpress for one of my sites and got the error similar to the following:

> Fatal error: Call to undefined function xmlrpc\_encode\_request() in /path/to/a/php/file on line x

This happened because the server did not have xmlrpc extension for PHP enabled. If you are getting this error on a shared hosting server, you are almost out of luck. However, you can still talk to support to have it installed. If you have your own VPS or Dedicated, you can install and configure it on your own. If you do not have it installed, you can install it by typing in the following (as root of course): Ubuntu:

apt-get install php5-xmlrpc

CentOS/Red Hat:

yum install php-xmlrpc

If it is already installed, but disabled, you can go to the following directory and enable it: Ubuntu: /etc/php5/conf.d/ CentOS/Red Hat: /etc/php.d/

Look for xmlrpc.ini. If it does not exist, create it. Now, make sure it has the following contents:

; Enable xmlrpc extension module
extension=xmlrpc.so

Make sure there is no semicolon in the beginning of second line. Save it.

Now, if PHP is loaded as apache module (most probably it is the case), you will need to restart apache for changes to take effect. Run the following to restart apache: Ubuntu:

service apache2 restart

or

/etc/init.d/apache2 restart

CentOS/Red Hat:

service httpd restart

or

/etc/init.d/httpd restart

Hope this helps.
