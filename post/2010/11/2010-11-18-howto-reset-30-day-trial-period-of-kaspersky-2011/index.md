---
title: "[HOWTO] Reset 30 day trial period of Kaspersky Pure, Kaspersky Internet Security 2011 and other products"
date: "2010-11-18"
tags: 
  - "kaspersky"
  - "windows"
---

_Disclaimer: This guide is for educational purposes only. If you wish to use Kaspersky products for more than 30 days, you must buy them from Kaspersky. I (or anyone else except you) am not responsible for any harm done to your installation or OS or Computer using information on this site. You have been warned._

I am writing this for Kaspersky Internet Security 2011 v 11.0.1.400 but it should work with other versions and other Kaspersky products; Kaspersky Pure, Kaspersky Antivirus 2011.

**Safety Instructions** This guide may cause your installation to be unusable. Make backups while making changes so that you can revert to backups if something unusual happens.

**Requirements** No extra tools are required. Just make sure you have the installer handy as the process involves re-installation of Kaspersky Software in question. Make sure you have Internet connection active when you are following the guide. Trial activation requires internet connection.

**Disable Self Defense** Kaspersky protects changes to its settings and files. Thus, Self Defense must be disabled before starting. Here is how: [How to disable self defense of KIS 2011](http://support.kaspersky.com/kis2011/tech?qid=208282021) [How to disable self defense of KIS 2010](http://support.kaspersky.com/faq/?qid=208280794)

**Exit Kaspersky** Right click on the system tray icon and exit.

**Remove Reports Directory** Reports directory is located in the following location if you are using Windows XP:

%AllUsersProfile%\\Application Data\\Kaspersky Lab\\AVP11\\

If you are using Windows Vista or Windows 7, here it is:

%SystemDrive%\\ProgramData\\Kaspersky Lab\\AVP11\\

The Reports directory probably contains reports of software. In addition it also contains information about the trial. So, remove it or move it to somewhere else. Don't remove just the contents but the directory itself.

**Remove Registry Keys** Kaspersky stores your license information in the following registry keys:

HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SystemCertificates\\SPC
HKEY\_LOCAL\_MACHINE\\SOFTWARE\\KasperskyLab\\protected\\LicStorage

Delete these keys, all subkeys and values. Here are the commands that do the same:

REG delete HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SystemCertificates\\SPC /f
REG delete HKEY\_LOCAL\_MACHINE\\SOFTWARE\\KasperskyLab\\protected\\LicStorage /f

**Reinstall Kaspersky** Run the setup of Kaspersky and re-install. At the end of the setup, the application should ask to Activate the trial.

**Reboot** Kaspersky setup will ask for rebooting. Reboot and a new 30 days trial license should be active.
