---
title: "[SOLVED] Blank dark screen after installing ATI Proprietary Drivers (fglrx) in Ubuntu 11.04 Natty Narwhal"
date: "2011-09-01"
categories: 
  - "natty-narwhal"
tags: 
  - "ati-radeon"
  - "fglrx"
  - "linux"
  - "plymouth"
---

Having video and sound issues with Fedora 15, I decided to try out Natty on my HP Pavilion G4 1009tx. Surprisingly, sound and 3D effects ran great with Intel onboard graphics so I installed it onto the Hard drive. In all excitement, I decided to try out proprietary ATI drivers for the switchable dedicated AMD Radeon HD 6470M graphics. However, when I rebooted, it would not boot. It seems that plymouth crashes and system ends up with a black screen. So, I decided to remove fglrx and keep on using Intel card but it seems that I can't even boot into recovery mode. So, I had to remove fglrx and make the system usable again using the Live CD and chroot. Here is how I did it.

**Note:** If you are trying to get the fglrx to work, you should look somewhere else. I just removed fglrx and decided not to use it (for now at least).

First, I booted into the Live Ubuntu Desktop. Then, I opened the terminal and created a directory for mounting everything:

sudo mkdir /mnt/root

Then I mounted the root partition.

sudo mount /dev/sda7 /mnt/root

Please note that my installation's root partition is /dev/sda7. In your case, it can be something else. Since I have a separate home partition (/dev/sda8), I mounted it too, just in case. You can skip this if you don't have a dedicated home partition.

sudo mount /dev/sda8 /mnt/root/home

You should also mount other drives if you have dedicated partitions for other directories (for /boot perhaps?).

Then, I mounted other required directories.

sudo mount -o bind /dev /mnt/root/dev
sudo mount -o bind /proc /mnt/root/proc
sudo mount -o bind /sys /mnt/root/sys

Then, I chrooted to the mounted root:

sudo chroot /mnt/root

Now, I got into the root of my installed Ubuntu. Then I just had to run the following to remove fglrx:

apt-get remove fglrx

UPDATE 1:  
(ignore this, see UPDATE 2 below)  
After upgrading xserver-xorg-video-all, xserver-xorg-video-ati and xserver-xorg-video-radeon, the screen went blank again after reboot. So, I had to downgrade the packages by downloading from repos. Here is how you can do it too (I have included the packages in an archive which you can download [here](https://mega.nz/file/9wZSlZKZ#LlK-cWQZBGGRH0xKuho1L3g_pobbdg_X8NtZO7DA9fk), please note that you need an active Internet connection for the following):

dhclient
cd /tmp
tar xzvf ˜/Downloads/xserver-ati-old.tar.gz
dpkg -i xserver-xorg-video-radeon\_6.14.0-0ubuntu4\_i386.deb xserver-xorg-video-ati\_6.14.0-0ubuntu4\_i386.deb xserver-xorg-video-all\_1%3a7.6+4ubuntu3\_i386.deb

UPDATE 2:  
This blank screen issue would still reappear once in a while and the laptop would get very hot over prolonged usage, so I decided to go for a slightly different solution. I removedxserver-xorg-video-radeon and xserver-xorg-video-ati, blacklisted the radeon module and disabled it via vgaswitcheroo. Here is how I did it:  
**Remove ATI Radeon drivers:**

apt-get remove xserver-xorg-video-ati xserver-xorg-video-radeon

**Blacklist kernel module:**  
To disable kernel module, I opened the file /etc/modeprobe.d/blacklist.conf and add a line 'blacklist radeon'. You can use nano to do this:

nano /etc/modprobe.d/blacklist.conf

Ctrl+O to save and Ctrl+X to exit nano.  
**Re-enable kernel module after startup and switch the card off:**  
To do this, I just added two lines before the line 'exit 0' in /etc/rc.local (you can use nano for this too) so that the file looks like the following:

#!/bin/sh -e
#
# rc.local
#
# This script is executed at the end of each multiuser runlevel.
# Make sure that the script will "exit 0" on success or any other
# value on error.
#
# In order to enable or disable this script just change the execution
# bits.
#
# By default this script does nothing.

modprobe radeon
chown USERNAME /sys/kernel/debug/vgaswitcheroo/switch
echo OFF > /sys/kernel/debug/vgaswitcheroo/switch

exit 0

In the file above, USERNAME is my login username. Don't forget to replace USERNAME with your username before saving the file. (If you are not sure what your username is, just do this: ls /home/, you should see it in the name of the directory.)

When done, I just exited from the chrooted environment:

exit

Then, I unmounted everything:

sudo umount -a

(You'll see some error messages, like device is busy, just ignore them)

Now, I am able to boot into the installed Ubuntu again. Hope this helps.
