---
title: "[SOLVED] Gtk-Message: Failed to load module \"rgba\": librgba.so: cannot open shared object file: No such file or directory"
date: "2010-03-13"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "librgba-so"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "module"
  - "nautilus"
  - "ppa"
  - "repository"
  - "rgba"
  - "synaptic"
  - "ubuntu"
  - "ubuntu-10-04"
---

I had enabled the ppa

ppa:erik-b-andersen/rgba-gtk

and upgraded and installed nautilus, murrine-themes , gtk2-module-rgba and gtk2-engines-murrine to enable rgba transparency in my Ubuntu 10.04 Lucid Lynx Alpha. That looks really cool. It was supposed to be coming with Lucid, but was dropped due to bugs. The programs started crashing for me too. I was done with adding exceptions to /etc/profile.d/gtkrgba.sh because almost every new program crashed. So I decided to remove the rgba module altogether. Just removing the repository does not help. So, here are the removal instructions.  
**Find and removing the PPA Packages and installing original versions:**  
Open up synaptic. Make sure you have not disabled the rgba repository.  
Click on "Origin" in the lower left of Synaptic and in the upper left pane, select LP-PPA-erik-b-andersen-rgba-gtk/lucid.  
Now, the packages installed via the repository can be seen in the main window of synaptic.  
Select gtk2-engines-murrine and click on Package>Force Version and choose non-ppa version. Repeat the same for libnautilus-extension1, murrine-themes and nautilus.  
Mark gtk2-module-rgba for removal.  
Apply the changes.  
Now, you can safely remove the PPA repository.  
**Remove the rgba module listing from profiles:**  
Even after the removal of ppa versions, you will still get a message

Gtk-Message: Failed to load module "rgba": librgba.so: cannot open shared object file: No such file or directory

if you launch an application from the terminal. To disable that, you will need to edit the /etc/profile.d/gtkrgba.sh and comment out all lines that are related to rgba. Default gtkrgba.sh looks like this:

export GTK\_MODULES=rgba
export GTK\_RGBA\_APPS=allbut:firefox:firefox-3.5:gksudo:ooffice:soffice:inksca\\
pe:gksu:gtk-recordMyDesktop:kompozer-bin:gpaint:lernid:totem:truecrypt:thunde\\
rbird-bin:thunderbird:checkgmail:gloobus-preview:exe:firefox-bin:swiftfox-bin\\
:gnome-mplayer:gnome-screensaver:google-chrome:chromium-browser:prism-bin:gno\\
me-mplayer

I opened the file as root (Alt+F2>gksu gedit /etc/profile.d/gtkrgba.sh) and commented out all the lines and saved it. Now, it looks like this:

#export GTK\_MODULES=rgba
#export GTK\_RGBA\_APPS=allbut:firefox:firefox-3.5:gksudo:ooffice:soffice:inksca\\
#pe:gksu:gtk-recordMyDesktop:kompozer-bin:gpaint:lernid:totem:truecrypt:thunde\\
#rbird-bin:thunderbird:checkgmail:gloobus-preview:exe:firefox-bin:swiftfox-bin\\
#:gnome-mplayer:gnome-screensaver:google-chrome:chromium-browser:prism-bin:gno\\
#me-mplayer

You may need to logout and re-login and you should no longer see the Warnings.

Hope this helps.
