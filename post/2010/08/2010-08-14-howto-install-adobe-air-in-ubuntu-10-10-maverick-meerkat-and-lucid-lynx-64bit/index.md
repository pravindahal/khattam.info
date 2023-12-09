---
title: "[HOWTO] Install Adobe AIR In Ubuntu 10.10 Maverick Meerkat and Lucid Lynx 64bit"
date: "2010-08-14"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "adobe"
  - "adobe-air"
  - "air"
  - "linux"
---

Here is how I installed Adobe AIR in Ubuntu 10.10 Maverick Meerkat Alpha 64bit. The same should work for Ubuntu 10.04 Lucid Lynx 64bit.

**Installing ia32libs**  
You probably have it installed already if you chose to install flash-player or some other application that makes use of 32-bit libraries. If you haven’t, you should install it from Synaptic Package Manager or by executing the following command in the terminal:

sudo apt-get install ia32-libs

**Getting Adobe Air Package/Installer** I downloaded bin version from [Adobe Air Download Page](http://get.adobe.com/air/). You can also choose deb version but it is not recommended as it causes problems that I will explain later.

**Installation** To install, make sure you have no synaptic or apt running. Launch the terminal and change the directory to where you have saved the deb file. For example, if it is the Downloads directory, type in:

cd ~/Downloads

Alternately, you can right click on the directory where the deb has been downloaded and select "Open in Terminal" (you will need to have nautilus-open-terminal installed for this) Now, execute the following command:

chmod +x AdobeAIRInstaller.bin
./AdobeAIRInstaller.bin

If you get the following error

> **Sorry, an error has occured** Adobe AIR could not be installed because another application is already being installed. Complete the first installation before proceeding with this one.

then just quit Synaptic or any other package manager you might be running and it should install fine.

If you downloaded deb version, then use the following:

sudo dpkg -i adobeair.deb

**Installation of AIR Applications** Now, you can install Air Applications. To do so, goto Applications>Accessories>Adobe AIR Application Installer. You can also open terminal and type in

Adobe\\ AIR\\ Application\\ Installer

You can just type in "A" and press TAB and it should work.

However I get the following error while running the application via terminal;

> /usr/lib/gio/modules/libgvfsdbus.so: wrong ELF class: ELFCLASS64 Failed to load module: /usr/lib/gio/modules/libgvfsdbus.so /usr/lib/gio/modules/libgioremote-volume-monitor.so: wrong ELF class: ELFCLASS64 Failed to load module: /usr/lib/gio/modules/libgioremote-volume-monitor.so /usr/lib/gio/modules/libgioremote-volume-monitor.so: wrong ELF class: ELFCLASS64 Failed to load module: /usr/lib/gio/modules/libgioremote-volume-monitor.so /usr/lib/gio/modules/libgvfsdbus.so: wrong ELF class: ELFCLASS64 Failed to load module: /usr/lib/gio/modules/libgvfsdbus.so

I have not experienced any problems with it. Select the AIR application and follow the on screen instructions. You can leave the install location as /opt and the application will be installed without problems. You should also see desktop shortcuts for installed AIR applications.

**Uninstallation of AIR Applications** Search for the application name in Synaptic Package Manager. You should be able to remove it from there.

**Uninstallation of Adobe AIR** If you don't need Adobe AIR anymore, you can remove it. To do so, search for Adobe AIR in Synaptic Package manager and remove it. This works only if you have installed via the bin version. The deb version does not show up. This is probably an issue with the current version and hopefully it gets solved in the next version (or do the programs installed with --force-architecture not show at all??). This is the reason why I did not recommend the deb installer. Worst of all, when you install the deb version, you see the AIR applications in package manager but there is no Adobe AIR and hence you have broken dependency problems. This will force you to remove all AIR applications before you can use Synaptic or any other package manager again.

Hope this helps.
