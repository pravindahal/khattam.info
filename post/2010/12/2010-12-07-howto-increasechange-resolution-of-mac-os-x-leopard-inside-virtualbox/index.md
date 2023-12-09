---
title: "[HOWTO] Increase/Change Resolution of Mac OS X Leopard inside VirtualBox"
date: "2010-12-07"
categories: 
  - "debian-linux"
  - "mac"
tags: 
  - "linux"
  - "virtualbox"
---

I have installed iATKOS S3 v2 inside VirtualBox running on Debian. It can be simply installed like any other Operating Systems, but if you choose Operating System as Mac OS X Server, you must uncheck Enable EFI in the settings dialog.

If you wish to install, make sure to install latest VirtualBox (at least v3.2.x) first.

After the installation is ready, I was having problems with resolution. The only resolution that was available was 1024x768. To change it, I performed the following process.

**I. Change com.apple.Boot.plist** 1. Open up Finder from the dock (left most icon by default). 2. Open the Partition where you have installed Mac OS X under Devices. 3. Now, if you have an Extras directory in root, look for com.apple.Boot.plist. If you don't, go to /Library/Preferences/SystemConfiguration/. You should see com.apple.Boot.plist 4. Copy the file com.apple.Boot.plist to Desktop. 5. Open the file on the Desktop with text editor (TextEdit). 6. Look for the following text:

GraphicsEnabler

If this value exists, the next line should have something like this:

 1280x768x32

Change it to whatever resolution your monitor supports. If the value does not exist, add the following before </dict>

        Graphics Mode
        1360x768x32
        GraphicsEnabler
        y

Make sure, you have entered proper resolution for your monitor.

The following is my complete com.apple.Boot.plist:

	Kernel
	mach\_kernel
	Kernel Flags
	
	Boot Graphics
	Yes
        Quiet Boot
        No
        Timeout
        5
        Graphics Mode
        1360x768x32
        GraphicsEnabler
        y

7\. Save the file to Desktop and close TextEdit. 8. Now, drag the file on the Desktop to the folder you copied it from. Confirm to Authenticate and Enter your password. Confirm to replace file. 9. Shut down Mac OS X.

**II. Add Custom Video Mode as extradata to VirtualBox Configuration** 1. Note your Virtual Machine Name for Mac OS X and quit VirtualBox. It is the name displayed in the Left Pane of the VirtualBox window. 2. Now, open up Terminal (or command prompt if you are using Windows) and run the following command (not as it is, make sure to make modifications. See below):

VBoxManage setextradata "Virtual Machine Name" "CustomVideoMode1" "\_required\_X\_resolution\_X\_colordepth"

For example, if you have a virtual machine named "Mac Test" and want to set a resolution of 1440x900, you must run the following command:

VBoxManage setextradata "Mac Test" "CustomVideoMode1" "1440x900x32"

Now, start VirtualBox and start the Virtual Machine, Mac OS X should now use the new resolution.

Hope this helps.
