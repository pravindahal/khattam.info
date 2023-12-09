---
title: "[HOWTO] Ease your eyes while using Linux with some RedShift"
date: "2010-06-06"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "10-10"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "maverick-meerkat"
  - "redshift"
---

I usually sit in front of my PC for long hours. It is always better to have least effect on my eyes and I used to reduce the brightness and adjust colors for that. Now, I have discovered a software to do just that. It claims to adjust the screen color temperature according to the surroundings. It is called Redshift and can be installed from the PPA ppa:jonls/redshift-ppa. To install it on Karmic and Lucid, open up Synaptic and navigate to Settings>Repositories>Other Software>Add and paste in "ppa:jonls/redshift-ppa" (without quotes) and then close it, Reload the package lists by clicking Reload in the Toolbar and then search for redshift and install it. It is not available for Maverick Meerkat now, but you can install it by following my [earlier post](http://www.khattam.info/2010/06/06/taking-care-of-ppas-after-distro-upgrade-to-development-version/). After installation, you can run it by invoking the following command from the terminal:

redshift -l LATITUDE:LONGITUDE

For example, since I am at Lalitpur, Nepal, I ran:

redshift -l 27.4:85.2

You can find latitude and longitude information about your city [here](http://www.stutzfamily.com/mrstutz/LatLong/latlonglist.htm). If you don't, use the one which is nearest to your place and it should work just fine. You will immediately see a change in color. You may also like it to show a tray icon so that you can disable/enable it easily if you have to. To do so, just run:

gtk-redshift -l LATITUDE:LONGITUDE

You can toggle enable/disable by clicking on the tray icon.

You will probably want to install run it on startup. To do so, just open Startup Applications and Add an application with command as

gtk-redshift -l LATITUDE:LONGITUDE

To see how much it is actually helping your eyes, keep it enabled for prolonged hours while you sit in front of your PC and disable it. You will see how difficult it is to see the normal color and how cool RedShift is.

Hope this helps.
