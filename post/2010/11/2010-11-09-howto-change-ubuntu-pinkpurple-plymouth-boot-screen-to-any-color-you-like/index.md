---
title: "[HOWTO] Change Ubuntu Pink/Purple Plymouth Boot screen to any color you like"
date: "2010-11-09"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "boot-screen"
  - "linux"
  - "plymouth"
---

I am using Ubuntu 10.10 Maverick Meerkat and have been using the default theme for quite some time. I was bored with the default boot screen and decided to change it. If you don't like the purple color of Ubuntu, you can easily change the Desktop theme and wallpaper, but the Pink/Purple Ubuntu Plymouth boot splash is a little difficult to get rid of. You can install other available boot splash by installing other packages, but I like the default boot screen, and just wanted to change its color. To do that, I just cloned the boot screen and made some changes so that it looks like the following.

![](images/plymouth-non-pink-preview.png "plymouth-non-pink-preview")

Here is how I did it. Fire up the terminal and get ready.

**Make a copy of the plymouth theme:**

sudo cp -R /lib/plymouth/themes/ubuntu-logo /lib/plymouth/themes/ubuntu-logo-nonpink

**Edit the name and location information:**

sudo gedit /lib/plymouth/themes/ubuntu-logo-nonpink/ubuntu-logo.plymouth

I changed the name to "Ubuntu Logo NonPink" and changed the location of ImageDir and ScriptFile so that it looks like the following:

\[Plymouth Theme\]
Name=Ubuntu Logo NonPink
Description=A theme that features a blank background with a logo.
ModuleName=script

\[script\]

ImageDir=/lib/plymouth/themes/ubuntu-logo-nonpink ScriptFile=/lib/plymouth/themes/ubuntu-logo-nonpink/ubuntu-logo.script

Save the file and exit.

**Edit the color in script:**

sudo gedit /lib/plymouth/themes/ubuntu-logo-nonpink/ubuntu-logo.script

Search for "Window.SetBackgroundTopColor" (without quotes) and change the 2 lines so that they look like the following:

Window.SetBackgroundTopColor (0.85, 0.85, 0.85);     # Nice colour on top of the screen fading to
Window.SetBackgroundBottomColor (0.75, 0.75, 0.75);  # an equally nice colour on the bottom

I have chosen these colors: #DADADA RGB: 217, 217, 217 and #C0C0C0 RGB: 192,192,192  
You can choose any color you like. Find the RGB using gcolor2 (install this if you don't have it installed) of the desired color and divide the RGB values with 256 to get the values to use.  
Save the file and exit.

**Edit the Ubuntu Logo and other images:**  
Install Gimp if you haven't already done so and run the following:

 sudo gimp /lib/plymouth/themes/ubuntu-logo-nonpink/ubuntu\_logo.png

The white logo may not look good with the background above. You may change the color however you like. For my selection of background color, black would look great, so I just inverted colors (Colors>Invert).  
Once done editing the image, save the file and quit Gimp.  
Now, change the progress dots:

sudo gimp /lib/plymouth/themes/ubuntu-logo-nonpink/progress\_dot\_on.png

sudo gimp /lib/plymouth/themes/ubuntu-logo-nonpink/progress\_dot\_off.png

I just changed the mode to RGB (Image>Mode>RGB) and desaturated the image (Colors>Desaturate) and got nice gray dot for progress\_dot\_on. I made no changes to progress\_dot\_off.

**Install the theme:**  
The theme is ready and can be installed using the following command:

sudo update-alternatives --install /lib/plymouth/themes/default.plymouth default.plymouth /lib/plymouth/themes/ubuntu-logo-nonpink/ubuntu-logo.plymouth 100

**Set the theme as default:**  
Once installed, it can be set as default using the command:

sudo update-alternatives --config default.plymouth

The above command lists all the installed themes as shown:

There are 2 choices for the alternative default.plymouth (providing /lib/plymouth/themes/default.plymouth).

  Selection    Path                                                            Priority   Status
------------------------------------------------------------
  0            /lib/plymouth/themes/ubuntu-logo-nonpink/ubuntu-logo.plymouth    100       manual mode
\* 1            /lib/plymouth/themes/ubuntu-logo/ubuntu-logo.plymouth            100       manual mode

Press enter to keep the current choice\[\*\], or type selection number:

Enter the number corresponding to the theme you want to use. In my case, it is "0". So I entered 0 and pressed ENTER. In your case, it may be different.

**Update Initial Boot Image**  
Now, you will need to run one more command to update the boot images and you are done.

sudo update-initramfs -u

Reboot and see the changed boot screen.
