---
title: "[SOLVED] LWP::UserAgent version 5.827 required--this is only version 2.033 at /usr/lib/perl5/vendor_perl/5.8.8/WWW/Mechanize.pm line 106"
date: "2010-09-25"
categories: 
  - "centos-rhel"
tags: 
  - "get_flash_videos"
  - "linux"
  - "mechanize"
  - "perl"
  - "useragent"
---

I installed an application get\_flash\_videos, which requires WWW Mechanize, on my Virtual CestOS 5.5 server. I installed it with yum:

yum install perl-WWW-Mechanize

When I ran the program, I got the following error:

> LWP::UserAgent version 5.827 required--this is only version 2.033 at /usr/lib/perl5/vendor\_perl/5.8.8/WWW/Mechanize.pm line 106

After searching on the Internet, I found that the error was due to bug in perl-libwww-perl-5.805-1.1.1.noarch. I found that upgrading it to perl-libwww-perl-5.827 would fix the issue. I found it [here](http://rpm.pbone.net/index.php3/stat/4/idpl/14465764/dir/redhat_el_5/com/perl-libwww-perl-5.827-1.el5.pp.noarch.rpm.html). I installed it with the following command:

rpm -Uvh ftp://ftp.pbone.net/mirror/ftp.pramberger.at/systems/linux/contrib/rhel5/archive/x86\_64/perl-libwww-perl-5.827-1.el5.pp.noarch.rpm

That fixes the problem and I can now run get\_flash\_videos.
