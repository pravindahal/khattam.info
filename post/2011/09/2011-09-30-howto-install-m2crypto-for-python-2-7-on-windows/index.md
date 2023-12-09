---
title: "[HOWTO] Install M2Crypto for Python 2.7 on Windows"
date: "2011-09-30"
tags: 
  - "windows"
---

I am using Windows 7 Home Premium 64-bit and had to setup M2Crypto required for a Python program that I am writing in Python 2.7 (32-bit). After hours of trying and searching, I finally managed to get it installed and working.

Here are some of the things that I tried, please move on to "**How I managed to get it to work**" if you don't want to go through boring "**What I tried**" stuff.

**What I tried:** First of all, I tried to install M2Crypto via pip. I got an error saying that swig.exe was not found, so I downloaded copy of swigwin and extracted it, then added the directory to system PATH. I installed easy\_install (setuptools), opened the terminal and changed dir to Python27\\Scripts and installed pip (easy\_install pip). Then, I tried to install M2Crypto using pip:

pip install M2Crypto

Unfortunately, I got the following error:

> SWIG\\\_m2crypto.i(31) : Error: Unable to find 'openssl\\opensslv.h'
> 
> SWIG\\\_m2crypto.i(45) : Error: Unable to find 'openssl\\safestack.h'
> 
> SWIG\\\_evp.i(12) : Error: Unable to find 'openssl\\opensslconf.h'
> 
> SWIG\\\_ec.i(7) : Error: Unable to find 'openssl\\opensslconf.h'
> 
> error: command 'swig.exe' failed with exit status 1

So, I downloaded openssl source files and copied the include directory to swig\_dir/lib, then I got errors that from swig. I also tried giving build\_dist parameter to setup.py but in vain. I was thinking of compiling openssl myself, but I figured that I would require Visual Studio (which I do not have). I thought of using MingW, but turns out you need to compile Python with MingW for it to work. I almost gave up on this, but I found that some developers had contributed build of OpenSSL and M2Crypto, so that I could just install them. Move on to next section to do it yourself.

**How I managed to get it to work** I downloaded pre-built binaries of M2Crypto built against OpenSSL 1.0 from [M2Crypto Wiki](http://chandlerproject.org/Projects/MeTooCrypto#Contributed%20Builds). The one that I downloaded is M2Crypto-0.21.1.win32-py2.7.msi. Then, I set it up. It detected my Python installation and installed the package. However, when I ran the Python script, I got the following error:

> import \_\_m2crypto ImportError: DLL load failed

I don't know if it was because I did not restart my computer after installation or if OpenSSL dlls were missing, in either case, you may want to install [Win32 OpenSSL V1 Light](http://www.slproweb.com/products/Win32OpenSSL.html) and install it and it should work.

Hope this helps.
