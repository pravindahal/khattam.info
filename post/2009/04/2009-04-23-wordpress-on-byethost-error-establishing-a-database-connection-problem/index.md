---
title: "Wordpress on ByetHost : \"Error Establishing a Database Connection\" Problem"
date: "2009-04-23"
tags: 
  - "byethost"
  - "web"
  - "wordpress"
---

I'm running this blog on a Free Hosting Plan provided by [Byethost](http://www.byethost.com). I recently ran into this problem and was thinking of asking for support but I figured out the problem and the solution to it.

What I had done recently was changed the password and failed to realize that it also changed the database and ftp passwords too. I conneted to the FTP using new password and edited the wp-config.php. I replaced the new password with the old one and thats it. Problem solved and the blog is back online.
