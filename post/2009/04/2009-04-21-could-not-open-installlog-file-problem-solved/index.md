---
title: "\"Could not Open Install.Log File!\" Problem Solved!!"
date: "2009-04-21"
tags: 
  - "count-not-open-installlog-file"
  - "installlog"
  - "install-log-file-missing"
  - "install-log-missing"
  - "missing"
  - "uninstall"
  - "windows"
---

You may have noticed a problem when uninstalling some programs, if you have Ntfs in Windows XP, Vista or 7, you are likely to face this problem. When you try to uninstall 'em from Add/Remove Programs List, they show a message "Could not Open Install.Log File!". This problem is generally seen with "Wise Installation Wizard". I have seen it only with "Wise Installation Wizard". I don't know if other installers give rise to same problem.

When you try to uninstall them from  
**_Start Menu_**\>>**_Programs_**\>>%**_ProgramName_**%>>**_Uninstall_**  
It again gives the same error.

This can be solved and the program can be un-installed without having to remove the directory, shortcuts and registry entries manually, which is really difficult and tiresome. I have found a solution to this problem and sharing with you all.

**Procedure:**  
1\. Open the directory where the program is installed. (Eg. For System Mechanic 5, By default, it is C:\\Program Files\\iolo\\System Mechanic 5, if you have installed XP on C:\\)  
2\. You will see a file named "Install.log" in there.  
3\. Move (cut and paste somewhere else) the "install.log" to say an empty new folder in desktop (first create a new folder and then paste the install.log into it).  
4\. Now, double click the un-installer (uninstall.exe or unwise.exe)  
5\. It will ask you to open the installation log. Locate to the "install.log" file on your desktop.  
6\. Now, uninstall will work fine and you can un-install the program.

**Alternate Procedure  
**You can simply drag the install.log to unwise.exe or uninstall.exe and it should work.

This should solve your problem and the program should be uninstalled.

Still Can't uninstall? Let me know in the comments.
