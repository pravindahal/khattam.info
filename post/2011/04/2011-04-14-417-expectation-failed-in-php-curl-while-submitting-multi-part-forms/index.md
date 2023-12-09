---
title: "[SOLVED] \"417 - Expectation Failed\" in PHP curl while submitting multi-part forms"
date: "2011-04-14"
tags: 
  - "curl"
  - "php"
  - "web"
---

I am using PHP Curl extension for a project which requires uploading file to a server I had no control over. However, I was getting HTTP Status 417 with error message Expectation Failed. I don't know what this is supposed to do and why curl sends it, so I tried removing it by overriding it with the following code:

curl\_setopt($curl,CURLOPT\_HTTPHEADER,array("Expect:  "));

It worked and the file uploaded successfully.

Hope this helps.
