---
title: "[SOLVED] API Key Installed but get the ERROR: WordPress.com Stats needs attention: please enter an API key or disable the plugin."
date: "2009-08-18"
tags: 
  - "web"
  - "wordpress"
---

I ran into this problem. I got an error with Wordpress.com Stats plugin. It was just a message but it looked ugly and although I had already installed API key and was getting stats, I wanted to remove it. Here is what I did.

I went into the database using phpmyadmin from my cPanel (your hosting may or may not have phpmyadmin, so you may want to edit the database some other way). I suggest you to backup your database, just in case you mess up.

Browse the wp\_options table and locate stats\_options. The value should look something like this: `a:7:{s:4:"host";s:16:"yourblogurl.tld/path";s:4:"path";s:1:"/"; s:7:"blog_id";i:blog_id_numeric;s:7:"version";s:1:"3";s:5:"error"; b:0;s:9:"key_check";b:0;s:7:"api_key";N;}`

Then edit it and change the value to null (i.e. delete the contents and leave it blank). Now, go to admin area of your blog and add the API key.

[![DreamTemplate - Web Templates](http://www.tqlkg.com/hj115y7B-53PTWRTQVZPRQUVZZXT)](http://www.jdoqocy.com/od98iqzwqyDHKFHEJNDFEIJNNLH)
