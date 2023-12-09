---
title: "[HOWTO] Configure remote connection to MySQL database server"
date: "2010-06-17"
categories: 
  - "hardy-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "dedicated-server"
  - "linux"
  - "mysql"
  - "nano"
  - "phpmyadmin"
  - "ping"
  - "remote-database"
  - "remote-database-connection"
  - "server"
  - "ubuntu"
  - "vi"
  - "virtual-private-server"
  - "vps"
  - "web"
---

I recently got a Ubuntu 8.04 Dedicated Server and wanted to move the database of one of my websites from my web host to the Dedicated Server while keeping the website in the web host. To do so, you must make sure you can connect to remote databases from your web host to the Dedicated Server (or VPS).

First, I exported the database from my web server into a .sql.gz file. You can choose .sql too. Then, I created a database (lets call it newdb) in the remote server using phpmyadmin (if you don't have phpmyadmin, you can install it in your dedicated server) and imported the database.

Now we move on to the remote privilege part. Login to your Dedicated Server via ssh. We will need to edit my.cnf (the MySQL configuration file) to make the mysql server bind to the IP of the Dedicated Server, not localhost or 127.0.0.1. We do that by typing in:

nano /etc/mysql/my.cnf

I use nano as my text editor, you may use vi or whatever text editor you want. Also, my.cnf is in /etc/mysql/my.cnf, yours might be /etc/my.cnf. Now, scroll down until your find

\[mysqld\]

Just a few lines below, you will find a line containing:

bind-address            = 

That line may be commented (with a # in the beginning) or may have localhost or 127.0.0.1 as bind-address. We do not want that. We want the IP of our dedicated server. Lets say it is 67.67.67.67, so the new line should look like:

bind-address            =  67.67.67.67

Save the file. If using nano, just press Ctrl+O and Enter. Press Ctrl+X to exit. If using vi, press Esc and type :w to save and :q to quit. Restart the mysql server by using the following command.

/etc/init.d/mysql restart

Now, fire up mysql:

mysql -u username -p

Enter password when asked. The username must be of an administrative user. Now, lets switch to the database we created earlier with phpmyadmin:

use newdb

That should say:

Database changed

Now, we create a new user and allow it to connect to the database:

grant CREATE,INSERT,DELETE,UPDATE,SELECT on newdb.\* to newuser@66.66.66.66;

where 66.66.66.66 is the IP of the web host. It can be found by pinging your domain. For example, if you have domain mydomain.com, you can simply do a:

ping mydomain.com

and find out the IP in terminal. It should give you something lie:

PING mydomain.com (66.66.66.66) 56(84) bytes of data.

Now, we set password for the user newuser. We do that by typing in:

set password for newuser@66.66.66.66 = password('mypassword');

Finally, we cleanup and exit mysql:

flush privileges;
exit;

Now, we are done. You can configure the website in the web host to connect to the database at your remote Dedicated Server with the following configuration (whatever applies to you): database=newdb username=newuser host=67.67.67.67

References: http://www.debian-administration.org/article/Adding\_new\_users\_to\_MySQL\_Databases http://www.debianhelp.co.uk/remotemysql.htm
