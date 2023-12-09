---
title: "[SOLVED] \"[ERROR] Fatal error: Can't open and lock privilege tables: Incorrect key file for table 'user'; try to repair it\""
date: "2011-04-15"
tags: 
  - "mysql"
  - "web"
  - "windows"
  - "xampp"
---

I am working on a computer with XAMPP installed on Windows 7. When I upgraded XAMPP to fix the earlier [problem with WinMySQLAdmin](http://www.khattam.info/solved-winmysqladmin-1-4-access-violation-at-address-xxxxxx-in-module-libmysql-dll-read-of-address-00000000-2011-04-15.html), a new problem with mysql was introduced. The error log (mysql\_error.log) showed the following entry at the end:

> \[ERROR\] Fatal error: Can't open and lock privilege tables: Incorrect key file for table 'user'; try to repair it

To fix, I downgraded to earlier version of XAMPP, exported the database and removed the mysql data directory, and reinstalled the latest version of XAMPP. Now, MySQL could start without problems. Then, I imported the data back and all was well.
