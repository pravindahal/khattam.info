---
title: "[HOWTO] Downgrading from Ubuntu 10.04 Lucid Lynx to 9.10 Karmic Koala"
date: "2010-03-15"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "04"
  - "10"
  - "9-10"
  - "downgrade"
  - "downgrade-from-lucid-to-karmic"
  - "downgrading-from-lucid-to-karmic"
  - "karmic"
  - "karmic-koala"
  - "koala"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lucid-to-karmic"
  - "ubuntu"
  - "ubuntu-10-04"
  - "ubuntu-9-10"
---

I was wondering if we could downgrade from Ubuntu 10.04 Lucid Lynx Alpha to Ubuntu 9.10 Karmic Koala. So I decided to put it upon test and I succeed. So, I am sharing this with those who wish to keep using stable Karmic Koala till the final version of Lucid is out.

Please note however, that all the installed applications will be lost, however the settings and files in your home directory will be preserved. So, for example if you have a huge list of saved sites on your Filezilla client, Filezilla will be gone, but when you install Filezilla on your Karmic, the settings should work. Also, your Firefox browsing history, preferences and other settings will also be preserved.

**DISCLAIMER: Please use the information at your own risk. I do not take responsibility of whatever damages you do to your Ubuntu installation, data or anything else by using the information in this tutorial.**

First, it is not a good idea to downgrade. If you are experiencing problems, you should try asking in ubuntuforums for help. You may wish to file a bug report too to help the developers fix it.

**Prerequisites:**  
Make sure you have the Human Theme set as your current theme and not one of the light themes that comes by default on Alpha 3 or any. You may also use a theme that you have installed manually to ~/.themes (from Appearance Preferences>Install)  
Backup critical data, just in case.  
Make a list of applications that you currently use, in case you are forgetful :D

**Procedure**  
I inserted the Karmic Koala CD-ROM into the drive and selected "Install Ubuntu". Then, I just selected my country and region. Then when the partitioning slide comes up, I selected "Specify Partitions Manually (Advanced)".

Then, I could see my parititon layout. I had installed Ubuntu in a single partition (with a separate swap partition though).

If you had selected a different physical partition for /home, you can simply choose to format the root (/) partition, and install Ubuntu over there. Even if that is the case, you should change the partition containing the /home directory to be mounted as /home so that it is not created in the same root partition. Also, select the same filesystem type you had (instead of "Do not use"). Also, if you wish to format, make sure you have backed up everything that has been saved to the root (/) partition. /var/www and MySQL databases are on the root partition, for example and not in the /home partition. Hence, these will be lost if you choose to format. There may be other files if you use other programs too, so make sure you know what you are doing.

If you had installed everything in the same partition i.e. no separate partition for /home or /etc or others, you should not mark the root partition for formatting as I have done. However, you must change it from "Do not use the partition" to the corresponding type you have used.

Review your partitioning setup and make sure of the formatting options (checked or unchecked as explained above, but the safe bet is to leave for not formatting in either case).

Now, this part is crucial. You must enter the same username that you previously used while installing (or any other user capable of using sudo or gksu i.e. in listed in the sudoers file may be used). You may choose to enter a different username and import user configuration later, but I haven't tried how it works, so I recommend you to use the same. I even chose the same password, but any other password should work.

Now, you should see a "Migrate documents and settings" window that lists the users that are on the system. You should not choose to import any of them if you have entered the same username in the previous step. However, if you haven't, you may choose to import settings. Again, as I have not tried this one, I cannot assure all other application settings will be restored.

Now, you can go ahead and continue the installation process.

If everything goes right, you must be able to boot into Karmic Koala and install the applications you were using with the same settings and data as in Lucid Lynx. It is highly recommended that you should upgrade to the latest packages using the update manager or Synaptic Package Manager.

Hope this helps.

Please do share your results.
