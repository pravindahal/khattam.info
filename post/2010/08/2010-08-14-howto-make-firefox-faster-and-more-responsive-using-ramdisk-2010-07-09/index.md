---
title: "[HOWTO] Make Firefox faster and more responsive using RAMDISK"
date: "2010-08-14"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "firefox"
  - "linux"
  - "optimize"
  - "ram-disk"
  - "ramdisk"
---

I am using Firefox 3.6.6 on my Ubuntu Maverick Meerkat Alpha and wanted to experiment with it.

Firefox uses the profile directory to read and write settings, bookmarks, saved passwords, extension preferences etc. When Firefox is launched, it reads those from profile directory and constantly accesses and writes information to the directory. I thought keeping this in RAM could make Firefox faster. To do so, I wrote a small script that copies the profile to RAMDISK and launches Firefox with that profile directory.

First of all, you will need to increase the RAMDISK size so that it can hold the profile directory. The profile directory can grow with cached files so you may want to limit caching appropriately by setting lower the values of browser.cache.disk.capacity and browser.cache.offline.capacity in about:config. You can set the RAMDISK size by editing /etc/default/grub and appending ramdisk\_size=SIZE\_IN\_BYTES to GRUB\_CMDLINE\_LINUX\_DEFAULT. To edit, you will need to open it as root (gksu gedit /etc/default/grub). The line should look like the following after the edit if you want the RAMDISK size to be approximately 256Mb:

GRUB\_CMDLINE\_LINUX\_DEFAULT="quiet splash ramdisk\_size=256000"

After saving the file, you need to run the following command from the terminal to update grub

sudo update-grub

Now, restart your computer for changes to take effect.

When this is done, save the following file as /usr/local/bin/firefox-ram. Uncomment (remove hash from) the line containing PROFILE\_PATH and change the path to your Firefox profile directory.

#!/bin/bash

# firefox\_ram v0.1 by \_khAttAm\_
# www.khattam.info
# July 09, 2010
# Needs RAM\_DEVICE larger than the size of profile directory
# Needs zenity installed
# Copyright (C) 2010  \_khAttAm\_

# will not run as intended and may cause data loss if profile directory
# is full or ramdisk is smaller than profile directory size

#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.

#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU General Public License for more details.

#    See .

# Change the following

PROFILE\_PATH=/home/pravin/.mozilla/firefox/e2k9jth5.default/

if \[ ! -n "$PROFILE\_PATH" \];
then
	zenity --info --text="Profile path not set. Please edit the script \\

	to set firefox profile path."
	exit
fi

USER\_NAME=$USERNAME
TMP\_PROFILE\_DIR=/home/$USERNAME/.mozilla/firefox/ramdisk/

RAM\_DEVICE=/dev/ram0

if \[ -f /tmp/firefox-ram-lock \]

then
	zenity --info --text="Only one instance is allowed. If no instances\\
	 are open, it may be performing post save operations. Please wait a\\
	 few moments and try again. If this persists and you are sure \\
	 nothing is going on, just remove /tmp/firefox-ram-lock and run \\

	 again."
	exit
fi

touch /tmp/firefox-ram-lock

echo "

umount $RAM\_DEVICE
mkdir -p $TMP\_PROFILE\_DIR
umount $TMP\_PROFILE\_DIR
mount -t ext2 $RAM\_DEVICE $TMP\_PROFILE\_DIR
">/tmp/firefox-ram-pre-pre.sh

chmod +x /tmp/firefox-ram-pre-pre.sh
gksu sh /tmp/firefox-ram-pre-pre.sh

# the following needs to be run as root

# this could be done by using gksu followed by command for each,
# but gksu has problem with commandline option -R
# hence the commands that need to be run as root are written to
# a temporary file and then executed using gksu
echo "
umount $RAM\_DEVICE
mke2fs $RAM\_DEVICE

mkdir -p $TMP\_PROFILE\_DIR
umount $TMP\_PROFILE\_DIR
mount $RAM\_DEVICE $TMP\_PROFILE\_DIR
">/tmp/firefox-ram-pre1.sh
chmod +x /tmp/firefox-ram-pre1.sh
gksu sh /tmp/firefox-ram-pre1.sh

PROFILE\_DIR\_SIZE=\`du -s $PROFILE\_PATH | cut -f1\`

#echo $PROFILE\_DIR\_SIZE

RAM\_DISK\_SIZE=\`df -k| grep $RAM\_DEVICE|cut -d' ' -f16\`

#echo $RAM\_DISK\_SIZE

if \[ "$RAM\_DISK\_SIZE" \\< "$PROFILE\_DIR\_SIZE" \];
then
	zenity --info --text="The size of RAMDISK ($RAM\_DISK\_SIZE bytes) is\\

	 not large enough to hold the profile directory \\
	 ($PROFILE\_DIR\_SIZE bytes). This program can't continue. Either \\
	 increase the size of RAMDISK or clear history and cache to reduce \\
	 the size of profile directory."
	rm /tmp/firefox-ram-lock
	exit

fi

echo "
cp -u -R $PROFILE\_PATH\* $TMP\_PROFILE\_DIR
chown -R $USER\_NAME $TMP\_PROFILE\_DIR
chmod -R 744 $TMP\_PROFILE\_DIR\*

">/tmp/firefox-ram-pre2.sh
chmod +x /tmp/firefox-ram-pre2.sh
gksu sh /tmp/firefox-ram-pre2.sh

echo \`date +%s\` > $TMP\_PROFILE\_DIR/firefox\_ram.chk

#run firefox with profile directory as the one in ramdisk

firefox -profile $TMP\_PROFILE\_DIR

#copy profile back to HDD
cp -u -R $TMP\_PROFILE\_DIR\* $PROFILE\_PATH

rm /tmp/firefox-ram-lock

Now, Alt+F2 and firefox-ram to run Firefox with profile from RAM. You should enter your password when asked as this is required to create and work with RAMDISK. The first launch can be a little slow, but subsequent launches should be quicker. You can also create a launcher in your dock or your Desktop for easy access.

Please note that when using this script, you should not switch between the other Firefox as that may cause data loss (loss of bookmarks, settings changes etc.). Also, you are advised to backup your profile directory regularly while using this script as it may cause data loss.

Please suggest improvements and changes in the script.
