---
title: "[HOWTO] Properly install VirtualBox 4 beta in Ubuntu/Debian/Linux Mint (and other Debian/Ubuntu derivatives)"
date: "2010-12-07"
categories: 
  - "debian-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "linux-mint"
  - "virtualbox"
  - "virtualbox-4"
---

I downloaded deb of VirtualBox beta 1 from [the beta packages page of Oracle website](http://download.virtualbox.org/virtualbox/4.0.0_BETA1/) and installed it. However, while launching Virtual Machines created with Oracle VirtualBox 3.x (closed source version), I got the following error:

> Failed to open a session for the virtual machine \[machine name\]. A virtual device is configured in the VM settings but the device implementation is missing. A possible reason for this error is a missing extension pack. Note that as of VirtualBox 4.0, certain features (for example USB 2.0 support and remote desktop) are only available from an 'extension pack' which must be downloaded and installed separately (VERR\_PDM\_DEVICE\_NOT\_FOUND).
> 
> Details: Result Code: NS\_ERROR\_FAILURE (0x80004005) Component: Console Interface: IConsole {515e8e8d-f932-4d8e-9f32-79a52aead882}

It was clear that it requires an extension pack. I went back to the download page and found an extension pack named "Oracle\_VM\_VirtualBox\_Extension\_Pack-4.0.0\_BETA1-68572.vbox-extpack" (newer versions may be available now so name may be different) and downloaded it. I installed it by double clicking it. It opens with VirtualBox by default (if it doesn't, open with and select VirtualBox). The following error popped up:

> Failed to install the Extension Pack /path/Oracle\_VM\_VirtualBox\_Extension\_Pack-4.0.0\_BETA1-68572.vbox-extpack. Failed to locate load the main module ('/usr/lib/virtualbox/ExtensionPacks/Oracle\_VM\_VirtualBox\_Extension\_Pack/linux.x86/VBoxPuelMain.so'): VERR\_FILE\_NOT\_FOUND.
> 
> Details: Result Code: NS\_ERROR\_FAILURE (0x80004005) Component: ExtPackManager Interface: IExtPackManager {8104df65-74d6-4e33-b374-50aa062b4afd}

When I tried to launch a Virtual Machine, I got the previous error. However, when I tried to reinstall the Extension, I got the following error:

> Extension pack 'Oracle VM VirtualBox Extension Pack' is already installed. In case of a reinstallation, please uninstall it first.

I learned from [WebUpd8](http://www.webupd8.org/2010/12/how-to-install-virtualbox-40-beta-in.html) that libstdc++5 was required for it. So, I just installed it by typing the following in terminal:

 sudo apt-get install libstdc++5

Then, after restarting VirtualBox, I was able to launch my Virtual Machines again.
