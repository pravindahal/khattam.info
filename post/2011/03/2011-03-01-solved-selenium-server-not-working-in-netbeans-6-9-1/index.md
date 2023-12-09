---
title: "[SOLVED] Selenium server not working in Netbeans 6.9.1"
date: "2011-03-01"
tags: 
  - "fedora"
  - "firefox"
  - "linux"
  - "netbeans"
  - "php"
  - "phpunit"
  - "selenium"
  - "web"
  - "yii"
---

I am using Fedora Core 14 and have installed Selenium Module for PHP. I was not able to run PHPUnit tests on Yii Framework. I tried running Selenium server 1.0.1 and upgrade to 1.0.3 solved the problem.

I downloaded the Selenium Remote Control from [here](http://selenium.googlecode.com/files/selenium-remote-control-1.0.3.zip) and extract the file selenium-server.jar, renamed it to selenium-server-1.0.1.jar and placed it in /home/myusername/.netbeans/6.9/modules/ext/selenium overwriting the old jar. Then I restarted Netbeans. Now, testing works.

Hope this helps.
