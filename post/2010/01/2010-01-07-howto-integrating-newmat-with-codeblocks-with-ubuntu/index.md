---
title: "[HOWTO] Integrating newmat with Code::Blocks in Ubuntu"
date: "2010-01-07"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "c"
  - "codeblocks"
  - "karmic"
  - "karmic-koala"
  - "linux"
  - "newmat"
  - "ubuntu"
---

Newmat is a matrix manipulation library for C++. It can be used with various C++ compilers.

Here we will go through how to use newmat with Code::Blocks in Ubuntu. I'm using Ubuntu 9.10 Karmic Koala with newmat 10 and Code::Blocks 8.02, however other versions may also work. Here is how you can do it.

Install libnewmat10-dev from Synaptic. Open Code::Blocks. If you want to add newmat to all your projects without having to care about setting it up in later projects of yours, you can edit the settings from Settings > Compiler and Debugger menu. However, if you want to add to particular project only, you will need to reach for Project > Build Options. Now, in the Linker tab, Add newmat. Now, you are ready to use newmat in your programs.

To use newmat, you will need to include newmat.h as follows at the beginning of your C++ project as follows: #include

You may also want to include iomanip and newmatio.h for operations such as c<<MATRIX, where MATRIX is an object of type Matrix. You can do that as follows: #include #include

Don't forget to use the following before you write any code: using namespace NEWMAT;

For more, view newmat documentation at http://www.robertnz.net/nm10.htm

Hope this helps.
