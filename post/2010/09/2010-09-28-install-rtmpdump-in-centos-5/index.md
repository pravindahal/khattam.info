---
title: "[HOWTO] Install rtmpdump in CentOS 5"
date: "2010-09-28"
categories: 
  - "centos-rhel"
tags: 
  - "libboost_regex-so"
  - "linux"
  - "openssl"
  - "rtmpdump"
---

I was trying to install rtmpdump on CentOS 5.5 32-bit. I tried some RPMs and failed. I got errors like:

> libboost\_regex.so.3 is needed by rtmpdump

Now I figured I had to compile from source. I installed the required dependencies:

yum install openssl-devel

Then I downloaded the source tarball for v2.2e:

wget http://rtmpdump.mplayerhq.hu/download/rtmpdump-2.2e.tar.gz

Then unpacked it:

tar xvf rtmpdump-2.2e.tar.gz

Then, compiled it:

cd rtmpdump-2.2e
make
make install

Now, run:

rtmpdump

If all goes well, you should get:

> RTMPDump v2.2e (c) 2010 Andrej Stepanchuk, Howard Chu, The Flvstreamer Team; license: GPL ERROR: You must specify a hostname (--host) or url (-r "rtmp://host\[:port\]/playpath") containing a hostname

Hope this helps.
