---
title: "[SOLVED] Fix the \"EXEs opening with a single program\" problem in Windows 7"
date: "2011-01-06"
tags: 
  - "exe"
  - "exe-problem"
  - "open-with-the-same-program"
  - "regedit"
  - "windows"
  - "winrar"
---

I was using a friend's computer with Windows 7 Ultimate 64bit with IDM installed. Once an EXE was downloaded, I clicked on "Open With" instead of Open and selected an application (WinRAR). Since the downloaded EXE file was a self extracting archive, I just wanted to view the contents using WinRAR. However, I neglected the grayed tick mark in "Always use the selected program to open this kind of file". After that, every program started opening with WinRAR. Even if you manage to delete the offending program somehow, you will get a "Windows cannot find .exe file. Make sure you typed the name correctly" and the problem will still not be fixed.

I searched around a lot to get rid of the problem but it was really difficult to find it. Finally I found [a solution by Vishal Gupta](http://www.askvg.com/solution-exe-files-always-open-with-notepad-or-other-applications/). However, it is not clear in his blog how to run the command. In my case, I was not able to open the command prompt either.

The solution is however, rather simple. If you have a browser open in the same computer, you are lucky. However, if you don't, I'm not sure how to go about it. Share if you know.

Anyways, here is the solution:  
Download and move the following file in the same folder:  
[exe.reg](https://mega.nz/file/N4J2FBAR#gDXolKArSXhbN59hC-L-BDOiAfDXdQ7_22nsSLJMUdo)

Now, open the directory and right click and merge it. That should make your programs launch properly now.
