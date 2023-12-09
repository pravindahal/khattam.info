---
title: "[HOWTO] Setup MySQL, Apache and PHP in Fedora 15"
date: "2011-05-29"
tags: 
  - "apache"
  - "fedora"
  - "httpd"
  - "linux"
  - "mysql"
  - "mysqld"
  - "php"
  - "phpmyadmin"
---

This is a simple guide to setup LAMP (Linux, Apache, MySQL and PHP). I am assuming you have Linux (Fedora 15) installed. The following commands will install the necessary packages to run Apache, MySQL and PHP.

su #for root login, enter password when prompted
yum install mysql-server
service mysqld start
mysqladmin -u root password PASSWORD\_HERE
yum install phpmyadmin

Now, you should have necessary packages installed. To run the apache and mysql services, enter the following in command prompt. This should be done each time you need to use unless you want those services to start with your OS.

su #for root login, enter password when prompted
service mysqld restart
service httpd restart

The directory where you can put in your files is /var/www/html/ and you can access phpMyAdmin by navigating to http://localhost/phpmyadmin

If you want the services to start with your OS, you will need to run the following:

su #for root login, enter password when prompted
chkconfig --add httpd
chkconfig httpd on
chkconfig --add mysqld
chkconfig mysqld on

Hope this helps.
