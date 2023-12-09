---
title: "[HOWTO] Add/Change plymouth theme in Debian Squeeze Testing"
date: "2010-11-19"
categories: 
  - "debian-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "plymouth"
---

If you are using Debian Squeeze, you can install plymouth and it will install some plymouth themes by default. You can list the installed themes by running the following command in the terminal:

/usr/sbin/plymouth-set-default-theme --list

If you wish to install a new theme and if the theme is meant for Ubuntu, you can't directly install it in Debian testing. If you get a deb, you will either get a failed dependency error like the following or it will not work even if you manage to install it:

> Error: Cannot install 'plymouth-label'

If you have a deb, open it up with file-roller (archive manager) and extract the directory which is inside ./lib/plymouth/themes in the deb archive. If you have a tarball (or some other archive) with instructions, just extract the directory.

Then, just copy the directory to /usr/share/plymouth/themes

If the directory name contains any capital letters, get rid of them and change the name such that the directory name is in all-lower-case. Also, get rid of spaces and such in the directory name. Inside the theme directory, you will see a .plymouth file. Open it up in a text editor and change the paths in it to /usr/share/plymouth/themes instead of /lib/plymouth/themes. Save the file and the theme is installed.

Now, run the following to list the themes:

/usr/sbin/plymouth-set-default-theme --list

You should see the newly installed theme listed. To change the theme, just run the following as root:

/usr/sbin/plymouth-set-default-theme theme-name

To test it, use the [plymouth-preview](http://www.khattam.info/plymouth-preview-a-tool-to-preview-your-plymouth-theme-2010-11-19.html) tool. To commit changes and rebuild initrd, use the following command as root:

update-initramfs -u

If everything goes well, the theme should be changed.
