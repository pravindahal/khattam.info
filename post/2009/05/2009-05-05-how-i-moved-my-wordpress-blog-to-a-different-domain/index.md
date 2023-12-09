---
title: "How I moved my Wordpress Blog to a different domain"
date: "2009-05-05"
tags: 
  - "askimet"
  - "migrating"
  - "web"
  - "wordpress"
  - "wordpresscom-stats"
---

I recently moved my Wordpress blog to different domain (from http://www.khattamonline.co.cc to http://www.khattam.info) and here is how I did it.

First, I followed the instructions at [this page](http://tamba2.org.uk/wordpress/move/ "Wordpress - Moving Domain Name"). The page suggested me to use [this windows program](http://www.tamba2.org.uk/wordpress/move/SCR.zip "SCR Freeware") and I did but there is another plugin for Wordpress to achieve the same.

Then, as Askimet gave me error at my new URL, I had to re-enter my Wordpress API key again and save it in the Askimet Configuration Page (Plugins>Askimet Configuration) to solve it. Also, I had to re-enter api-key at Wordpress.com Stats Plugin Configuration (Plugins>Wordpress.com Stats). It also provided me option to replace my blog with the new one in Wordpress Dashboard.

Now, i wanted the older domain and older links to point to my current domain. For this, I replaced the .htaccess in the old site directory with new one as mentioned [here](http://www.wptavern.com/two-wordpress-migration-tips "Two Wordpress Migration Tips").
