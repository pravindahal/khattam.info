---
title: "[HOWTO] Uploading photos to Facebook with Picasa on Ubuntu 9.10 (Karmic Koala)"
date: "2009-10-31"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "64bit"
  - "9-10"
  - "facebook"
  - "ie4linux"
  - "ies4linux"
  - "karmic"
  - "karmic-koala"
  - "koala"
  - "linux"
  - "picasa"
  - "ubuntu"
  - "ubuntu-9-10"
  - "web"
  - "wine"
---

UPDATE Nov 2, 2008: If you don't want to get into trouble installing Windows version of Picasa and happy to use F-spot instead, head over to the new article [here](http://www.khattam.info/2009/11/01/howto-upload-multiple-photos-to-facebook-using-f-spot-photo-manager-from-ubuntu-9-10-karmic-koala/).

The picasa application from Google repositories with Facebook button does not work for Facebook photo uploads. It ends up with a blank window with nothing but a link. However, I have found an alternative in Ubuntu Forums and it works.

The trick is to install Windows Internet Explorer under wine and then install the Windows version of Picasa. To do this, make sure you have wine installed and picasa removed from your system. This is how you do it: Open terminal and then create a directory

mkdir ielinux

Download ies4linux, the internet explorer installer for linux and run it.

wget http://www.tatanka.com.br/ies4linux/downloads/ies4linux-latest.tar.gz
tar zxvf ies4linux-latest.tar.gz
cd ies4linux-\*

Now run the following command

./ies4linux

If you do get an error, close the dialog and run it again as long as it is not completely installed. After it is done, type in the following:

wget http://www.khattam.info/junk/picasadownloader.sh ; chmod 777 picasadownloader.sh ;./picasadownloader.sh

The installer will automatically be launched. Perform the setup as you would do on Windows. Now, install facebook button. To do so, run the following command

wget http://www.khattam.info/junk/fbbtndownloader ; chmod 777 fbbtndownloader ;./fbbtndownloader

Now install picasa launcher. To do so, run the following set of commands

wget http://www.khattam.info/junk/picasa
sudo cp picasa /usr/bin/picasa
sudo chmod 777 /usr/bin/picasa

Now, launch picasa by running picasa from the terminal or from Run Applications Dialog (Alt+F2).

To upload pictures, select the pictures and click the Facebook button. You will be asked to login, select or create the album and then photos will be uploaded. See your album on Facebook to confirm the pictures.

If picasa stops responding, you can kill it by typing in the following command:

killall wineserver

Source : http://ubuntuforums.org/showthread.php?t=1093761
