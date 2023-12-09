---
title: "Turbo C++ IDE - Running on Linux, Windows Vista, Windows 7 or Mac OS"
date: "2009-05-04"
categories: 
  - "mac"
tags: 
  - "linux"
  - "mac-os"
  - "turbo-c"
  - "windows"
  - "windows-7"
  - "windows-vista"
---

Please look at the [alternatives for Turbo C++ IDE](http://www.khattam.info/2009/05/04/turbo-c-ide-a-look-at-the-alternatives/ "Turbo C++ IDE - A look at the Alternatives") before reading this post. Continue reading it only if you want to use BGI graphics (consider Allegro Gaming Library if you want an easy to use Graphics solution for C\\C++) or for code compatibility with your Textbook. You might consider changing your textbook if your School/College/University allows for new code. Continue only if you have no other option than using the DOS based Turbo C++ 3.0.

You will want to follow the tutorial if you plan to use Linux, Mac OS, Windows Vista or Windows 7 but have to use Turbo C++ in full screen environment so you are stuck with Windows XP or older version of Windows. Installtion Of Dosbox [Dosbox](http://www.dosbox.com/ "DosBox") is an x86 emulator with dos. It is available for Linux, Windows and Mac. It can be used to run legacy DOS applications and Games. We will use to run Turbo C++.

Dosbox may be present in the repository if you use Linux. Use your package manager to install dosbox.

Windows and Mac installers/binaries can be found in [the official website](http://www.dosbox.com/ "Dosbox").

One-Time Setup Place the installed Turbo C++ or Turbo C++ Setup in a folder. You might want this folder to mount as drive inside the dosbox. For that find the [dosbox.conf](http://www.dosbox.com/wiki/Dosbox.conf "dosbox.conf") file and add appropriate lines in the \[autoexec\] section. For example, if you want to mount a directory c:\\MyDosFiles as c:, then you must write the following in the dosbox based on your OS. For Windows (Vista or 7) you will need to add the following lines: `mount c c:\MyDosFiles` In Linux and Mac, if the directory is in /home/username, it will be something like: `mount c /home/username/MyDosFiles`

If you just plan to use Turbo C, you might as well launch the Turbo C++ IDE each time you start dosbox by adding folowing extra lines in dosbox. `c: cd tc tc.exe`

Also, you might want to add `fullscreen = true` at the top of the dosbox.conf file to start it in full screen.

Now, you can Launch dosbox and enjoy.

To quit, you will need to quit the IDE and type in exit at the prompt.

Hope this helps. Please post back comments and feedback. Also share if you get stuck somewhere.
