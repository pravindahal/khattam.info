---
title: "The tazebama Trojan Q &amp; A"
date: "2009-04-23"
tags: 
  - "tazebamadll"
  - "tazebamadl_"
  - "virus-removal"
  - "windows"
---

Section 0 **Disclaimer** This article is based on the author(\_khAttAm\_, thats me)'s own experience with the trojan and his own views. Please do understand that anything written here is for information only. The author or the owner of the site hosting this tutorial is not responsible for whaterver you do with the information from this article, only you are. USE THE INFORMATION AT YOUR OWN RISK.

Section 1 **How Does this trojan infect my Windows PC?:** You run the infected exe or the exe that it creates in all drives (except C:) with various names and icons.

Section 2 **What happens after execution of such exes?** The virus code runs which creates "c:\\Documents and Settings\\tazebama.dll" and loads the dll and calls it. The dll creates "c:\\Documents and Settings\\tazebama.dl\_" which is actually an executable (exe but the extension is dl\_) and executes it. The function also rebuilds the code in the Program Entry Point and calls it in case of infected exes. Then, the infected exes run as they would have if they were not infected. The exes that have CRC or some other self-integrity-check might fail to run because the exe has been modified. However, if some program has a partial integrity check and checks in the memory (to protect against loaders and patching too) then it runs fine coz the memory contents are re-created and it does not know that it is infected.

Section 3 **What is changed in infected exes?** Virus code is implanted starting from the Entry Point of the exe. The code at that place is copied with some protection and placed somewhere inside the exe (this is why the program size increases upon infection). This data is used as described in Section 2 to re-create Program Code to run later.

Section 4 **What does tazebama.dl\_ do after execution?** After execution, tazebama.dl\_ searches for infectable exes(I don't know the criteria of selection of EXEs) in all drives(including external portable ones) and infects them. The infected exes have the properties as described in Section 2. It also creates various exes with various names from its database (which is probably inside the exe in some encrypted form. I cudn't find the complete list) and selects a random icon (I don't think it is completely random icon. I think it is somehow associated with the name and most probably the information is in the database too) from shell32.dll. It also creates autorun.inf in all drives and zPharaoh.exe in all the drives. This exe is similar to the exe that it creates elsewhere and has an icon like default Windows Folder (Open). It also creates autorun.inf and zPharaoh.exe in "C:\\Documents and Settings\\%username%\\Local Settings\\Application Data\\Microsoft\\CD Burning" so if you burn a CD, the CD gets infected too. It also performs various other tasks that are not known to me. It keeps on running and repeats the process.

Section 5 **Symptoms Plz??** 1. The infected exes have increased size. 2. Creation of zPharaoh.exe in each drive as a hidden system file. 3. Creation of exe files with names like "JetAudio Dump.exe", "games+flash.exe", "what happens in vegas .exe", "Software.exe", "LockWindowsPartition.exe", "Win98compatibleXP.exe", "WinrRarSerialInstall.exe" etc in various folders of all drives (except C:). 4. Creation of "Documents and Settings\\tazebama.dl\_", "Documents and Settings\\tazebama.dll", "Documents and Settings\\hook.dl\_" 5. Increased load time of exes and extremely slow performance due to increased disk activity. 6. Frequent crashing of programs.

Section 6 **What about the remover??** The removal of this trojan is virtually impossible because it encrypts the original exe data. (The name of the function is something like VirtualProtect) However, I have thought of two kinds of removers that might be created if somebody can give enough time and have enough patience. **Remover Idea 1:** A possible remover(or let me say disabler) should be able to identify infected exes, and replace the virus code with modified virus code which only loads (without recreating it) and calls patched tazebama.dll(which must be modified to create the original exe code only and not to create and launch tazebama.dl\_). See Section 2 for details. However, this is not a removal and self-integrity-checking exes will still have problems as original code has been modified. **Remover Idea 2:** Another possible remover should call the function(which might should probably be to be modified to meet the needs) of tazebama.dll to recreate the exe code from the encrypted data stored inside the infected exe itself. It will also need to remove encrypted part from where it has been added to make the exe as it was before so that self-integrity-checking exes will also not have problems any more. Both these types of removers should also clear extra mess that has been created due to this virus.

Section 7 **I don't care how you can create a remover. How do I get this trojan off my system?** Calm down. Until someone codes a remover, we have nothing much to do about this trojan. However, a full re-format of **all drives** (including removable media that has been infected) is obvious solution, you might want to backup your data. Since most exes are infected, do not think about backing up programs (even setups) unless they had been enclosed inside zip (or rar or similar) file from before your PC was infected. Also, do not use Windows Default Burner (if you wish to backup in a CD) because it will lead to the infection of CDs too. When you add folders using Nero (or similar Burning Program), don't forget to remove exes from all the folders so that you don't burn the virus or infected exes too. This is one of the safest option to backup. Using alternate install of Linux to backup to DVDCD is more safe.

If you wish to backup in some external drives, you might be safe using other Operating System (like Live Linux) or your other drive and all the exes inside it will be infected too. Also, take special care not to backup exes or virus itself too. This is also very safe if you use Linux. However, if you use another Windows installation, be really really careful and use third party explorer (not the windows explorer) or do not double click to open infected drives so that you do not end up infecting the other system too. And many exes look like folders, so be very careful. After you are done, search and delete all the exes in the drive where you backed up your data.

If you don't have an option but to use the infected system to backup on some portable external drive, then follow the following procedure and take utmost care. 1. Download Process Explorer. 2. Run Process Explorer. 3. Look for tazebama.dl\_ in Process Explorer and kill it. If you came to this step from step 2, goto step 3, else return to the step next to that step which called this step. 4. Now connect your external device (which is blank and does not contain anything else, ok if you have something but make sure that there are no exes). 5. Call step 3. 6. Now, do not right click or press delete on any item coz this might activate tazebama.dl\_ again (This happens if you have verclsid.exe in your system32 folder, only some versions of WinXP have this). Yes thats true. Use Drag and Drop only for file transfer. Else use alternate explorer (not Windows explorer but some other file managing applications for Windows). If you wish to use Windows explorer and still want to perform normal copymove operations (this is not recommended at all), you might want to replace verclsid.exe with the uninfected one. Complete all the backup operation before moving to next step. 7. Call step 3. 8. Search for "\*.exe" in the drive where you chose to backup and delete all what is found. Search once more and if you still find them, you did not perform step 7 properly. 9. Search for System Hidden files autorun.inf and zPharaoh.exe in the external drive and delete it too. 10. Call step 3. If you had to kill tazebama.dl\_ in step 3 when called from this step, goto step 8. If you get into an inside an infinite loop, quit. 11. Now, disconnect your external drive immediately. 12. Reformat all drives and reinstall Windows (Install Linux if you do not ever wish to get infected with this virus .. But the choice is up to you.)

If you do not have an external device to back up your data, then you might wish to use other drives to backup. Follow the steps as explained above, and you should figure out what modifications you will need to make to do this.

Section 8 **Comments/Suggestion** I still don't know many things about this virus. If you have found anything else or if you find me wrong, please do let me know.

Section 9 **Where did you learn English??** Sorry for my poor English. It is not my native language.

Section 10 **Are you not going to thank me for reading the boring worthless Q & A??** Thank you for your patience.

This article was originally posted in [Mazzako Forum](http://forum.mazzako.com/index.php?topic=16508 "Original Post In Mazzako Forum").

**UPDATE**: [Download Tazebama Remover](http://www.avg.com/virus-removal.ndi-93495 "Tazebama Remover from Grisoft")