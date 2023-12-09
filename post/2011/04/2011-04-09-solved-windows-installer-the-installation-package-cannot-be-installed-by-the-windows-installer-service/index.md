---
title: "[SOLVED] Windows Installer: The installation package cannot be installed by the Windows Installer service."
date: "2011-04-09"
tags: 
  - "msinet"
  - "windows"
  - "windows-installer"
---

I ran into a computer with Windows XP and I got the following error while trying to install a new Windows application:

> **Windows Installer** This installation package cannot be installed by the Windows Installer service. You must install a Windows service pack that contains a newer version of the Windows Installer service.

I did not have time to install all automatic updates or install the whole service pack, so I downloaded a Windows hotfix from [here](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=5a58b56f-60b6-4412-95b9-54d056d6f9f4&displaylang=en). The file is named WindowsXP-KB942288-v3-x86.exe. I installed it and the program could be installed without problems.
