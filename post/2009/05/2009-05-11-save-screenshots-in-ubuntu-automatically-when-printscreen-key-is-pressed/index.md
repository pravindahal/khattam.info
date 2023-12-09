---
title: "[HOWTO] Save Screenshots in Ubuntu Automatically when PrintScreen key is pressed"
date: "2009-05-11"
categories: 
  - "ubuntu-linux"
tags: 
  - "bmp"
  - "gnome-screenshot"
  - "jaunty"
  - "jpeg"
  - "jpg"
  - "linux"
  - "print-screen"
  - "printscreen"
  - "scrot"
  - "ubuntu"
---

When you press the PrintScreen key in Ubuntu, you will see a gnome-screenshot dialog box with options to save the image or Copy it to clipboard. This function is great unless of course, you mistakenly press the key several times day which is really irritating. How about silently saving the image to some predefined location rather than popping up the dialog?  
  
To achieve this, we will use a command-line screenshot tool called scrot. You must install this via Synaptic Package manager or from the terminal by executing **sudo apt-get install scrot**. You may need to enable additional repositories if you do not find the program in the list.

Now, open up gedit as root by pressing Alt+F2 and typing in **gksu gedit** and then paste in the following code:  
#!/bin/sh  
mkdir ~/screenshots  
scrot ~/screenshots/$(date | sed s/ /-/g | sed s/://g).png

UPDATE: The code does not work due to wordpress replacing certain characters. Please use [this file](https://mega.nz/file/9pBEjDYA#5Mm9Q4vsEqtEJhWUTA8j3FpkM_fQbnPQZPTty0NyIl4) instead. Save it anywhere and then open it and copy the code to paste as suggested above.

EDIT: Replace png with jpg for jpeg format. Scrot will automatically save the image as jpeg. Other valid filetypes are bmp and tiff.

Save the file in **/usr/bin/scrot-sreenshot** (any name can be choosen but if you wish to save it with the different name, also change the occurances of the name in other parts as required). Close gedit and open up gnome-terminal. Now, in the terminal type in **sudo chmod 755 /usr/bin/scrot-screenshot**.

Now, we will depend on Compiz Commands. To be able to configure compiz, you will need to install **CompizConfig Settings Manager (compizconfig-settings-manager**). To do so, search for the package in Synaptic and install or type in **sudo apt-get install compizconfig-settings-manager**.

Open up **CompizConfig Settings Manager (System > Prefernces > CompizConfig Settings Manager)** and click on **Commands** and enable it. In any **Command-line** field in the **Commands** tab, type in **scrot-screenshot**. I chose **Command line 0**. Now, in the **Key Bindings** tab, in **Run Command 0**, if you selected **Comand line 0** in the previous step, Click on the button (which says **Disabled** if it was not previously configured) and tick the checkbox saying **Enabled**. Then, click on **Grab Key Combination** and press PrintScreen. It will warn you that the key is already being used by **Take a Screenshot and provide you wit**. Disable **Take a screnshot** and you are ready to go.

Now, try pressing **PrintScreen**, and you will see that the screenshots are already being saved to **screenshots** directory inside the **home** directory and annoying dialog is shown no more.

Post CommentsFeedback or if you faced any problems following the tutorial.
