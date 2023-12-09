---
title: "[SOLVED] CMake Error: your CXX compiler: \"CMAKE_CXX_COMPILER-NOTFOUND\" was not found.   Please set CMAKE_CXX_COMPILER to a valid compiler path or name."
date: "2010-12-20"
tags: 
  - "cpp"
  - "fedora"
  - "gcc"
  - "gcc-c"
  - "linux"
---

I am running Fedora KDE Spin. I was trying to compile a program. I tried running cmake but I got the following error:

> CMake Error: your CXX compiler: "CMAKE\_CXX\_COMPILER-NOTFOUND" was not found. Please set CMAKE\_CXX\_COMPILER to a valid compiler path or name.

I already had gcc and cpp packages installed but I was still getting the above error.

I later figured that the package gcc-c++ was not installed. I installed it via yum and the error was gone:

yum install gcc-c++

Hope this helps.
