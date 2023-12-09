---
title: "[HOWTO] Compile Facebook hiphop-php in Fedora 15"
date: "2011-06-29"
tags: 
  - "c"
  - "fedora"
  - "hiphop"
  - "hiphop-php"
  - "linux"
  - "php"
---

HipHop for PHP is a source code transformer which transforms PHP code to C++ and compiles it with gcc/g++. I wanted to experiment with it and tried to install in on my PC with Fedora 15. Here is how I did it and how you can do it ( hopefully :) ). Please note that this did not work and I will update the article soon.

**Install Dependencies Available in the Repos**  
In the terminal, run the following command:

su -c 'yum -y install git cmake boost pcre-devel libicu-devel libmcrypt-devel oniguruma-devel mysql-devel gd-devel boost-devel libxml2-devel libcap-devel binutils-devel flex bison expat-devel re2c tbb libmemcached-devel tbb-devel bzip2-devel openldap-devel readline-devel libc-client-devel pam-devel gcc-c++ memcached'

**Setup build environment**  
I compiled it in dev folder of home directory. Change directory in subsequent commands if you are doing it somewhere else. Run the following commands:

cd
mkdir -p dev/local

**Download hiphop-php**

cd
cd dev
git clone git://github.com/facebook/hiphop-php.git

**Download, patch and compile libcurl and libevent**  
Use these versions because as of current, patches for these versions are only available in hiphop git.

cd
cd dev

wget http://curl.haxx.se/download/curl-7.20.0.tar.bz2
wget http://www.monkey.org/~provos/libevent-1.4.13-stable.tar.gz
tar xvzf libevent-1.4.13-stable.tar.gz
tar xvjf curl-7.20.0.tar.bz2

export CMAKE\_PREFIX\_PATH=\`pwd\`/local

cd libevent-1.4.13-stable
cp ../hiphop-php/src/third\_party/libevent-1.4.13.fb-changes.diff .
patch < libevent-1.4.13.fb-changes.diff
./configure --prefix=\`pwd\`/../local
make install
cd ..

cd curl-7.20.0
cp ../hiphop-php/src/third\_party/libcurl.fb-changes.diff .
patch -p0 < libcurl.fb-changes.diff #see note-1 below

**Note-1:** While patching curl, you may be asked paths to the files. Enter includes/curl/multi.h and lib/multi.c respectively.

Now, you will need to make a small change in Makefile for it to compile properly. To do that open the file src/Makefile in gedit or any text editor, find the line that has the following:

curl\_LDADD = $(top\_builddir)/lib/libcurl.la -lz

and append -lrt so that the line looks like the following:

curl\_LDADD = $(top\_builddir)/lib/libcurl.la -lz -lrt

Now, run the following in the terminal:

cd
cd dev/curl-7.20.0
./configure --prefix=\`pwd\`/../local
make install
cd ..

**Compile hiphop-php**

cd
cd dev
export CMAKE\_PREFIX\_PATH=\`pwd\`/local
cd hiphop-php
git submodule init
git submodule update
export HPHP\_HOME=\`pwd\`
export HPHP\_LIB=\`pwd\`/bin
cmake . #see note-2 below
make #see note-3 below

**Note-2:** You may get errors while running cmake. This may be because of dependencies I might have missed above. In that case, please let me know the output of cmake in the comments so that I might be able to help.  
**Note-3:** If you encounter any errors while using make, remove CMakeCache.txt and run make clean, cmake and make again.

This should have worked, but I am getting the following error:

> ../../bin/libhphp\_runtime.a(ext\_mysql.cpp.o): In function \`HPHP::php\_mysql\_do\_query\_general(HPHP::String const&, HPHP::Variant const&, bool)':  
> ext\_mysql.cpp:(.text+0x8100): undefined reference to \`cli\_safe\_read'  
> ext\_mysql.cpp:(.text+0x826a): undefined reference to \`net\_field\_length'  
> ext\_mysql.cpp:(.text+0x83a0): undefined reference to \`cli\_safe\_read'  
> ext\_mysql.cpp:(.text+0x8712): undefined reference to \`free\_root'  
> collect2: ld returned 1 exit status  
> make\[2\]: \*\*\* \[src/hphp/hphp\] Error 1  
> make\[1\]: \*\*\* \[src/hphp/CMakeFiles/hphp.dir/all\] Error 2  
> make: \*\*\* \[all\] Error 2

It seems like a problem with mysql version in the Fedora repo. I will download and build mysql and update this post.

**Further Reading**  
https://github.com/facebook/hiphop-php/wiki/running-hiphop

**References**  
https://github.com/facebook/hiphop-php  
http://www.ioncannon.net/programming/918/building-hiphop-php-for-fedora-12-on-64-bit-and-32-bit-systems/  
http://comments.gmane.org/gmane.comp.web.curl.library/29278
