---
title: "Configuring CDMA Wireless Modem in Linux"
date: "2009-04-30"
tags: 
  - "cdma"
  - "jaunty"
  - "linux"
  - "ubuntu"
  - "utl"
  - "wireless"
---

UTL has been providing Wireless Internet Connection for over four months now and many Nepali have been using it as the only way to browse the internet. However, many users have have failed to configure the low cost brandless (or with some brand like Glink, Blink etc) USB modems in Linux. I will try to help you to configure your UTL Wireless modem to work under Linux.

First of all, you will need to check whether your usbserial device is detected as an ACM device or just a USB device.

To do so, disconnect your modem and re-connect it again, wait for a while, and type in the following in terminal: $ modprobe cdc\_acm

Now, type in $ dmesg | tail

If you see something like the following, "ttyACM0: USB ACM device", your device is detected as USB ACM device. If  you see something like "converter now attached to ttyUSB0" instead, your modem is not detected as ACM device but a USB device. If you see nothing like the above mentioned, your modem may not work with Linux.

If your device is detected as an ACM device, you are lucky and your modem will most probably work with Linux. Make sure you have wvdial installed\*,  and just do a $ wvdialconf as root\*\* and your modem must be detected. If you see something like: Found an USB modem on /dev/ttyACM0. Modem configuration written to /etc/wvdial.conf. Now, edit your wvdial.conf with your favourite editor as root\*\*\* and enter your Username, Password and Phone Number and save the file. Now, run wvdial as root and you should be connected to the internet.

If your device is not detected as an ACM device, you should try $ wvdialconf as root once and if your modem is detected (which is very less likely), you can follow the procedure explained above. If it is not detected, open up /etc/wvdial.conf with your favourite text editor as root\*\*\*, enter the following text replacing the original contents and save the file. Replace myphonenumber with your phone number. ;---------------- ;Thanks to mazzako forum member adimn for posting this \[Dialer Defaults\] Modem = /dev/ttyUSB0 Baud = 230400 Init1 = ATE0 #Init2 = AT$PBTYPE=1 RPTCON=1 MTRPTTYPE=3 SMSRUIM=0 SMSTYPE=1 Init3 = AT+CTA=0 Init4 = ATEOV1 Init5 = AT Init6 = ATS0=0 ISDN = 0 Modem Type = Analog Modem Phone = #777 Username = myphonenumber@utlnepal.com Password = myphonenumber Stupid Mode = 1 New PPPD = yes ;----------------

Now, run $ wvdial as root and you should be connected if you are lucky. Try a few times before you give up.

\* Jaunty Jackalope does not have wvdial installed by default. To install it, follow the [older post](http://www.khattam.info/2009/04/26/install-wvdial-in-jaunty-jackalope-offline/ "Install wvdial in Jaunty Jackalope Offline"). \*\* In Ubuntu, you should run programs $ sudo wvdialconf and enter your user password when asked. \*\*\* You can run $ gksu gedit /etc/wvdial.conf and enter password for your user, if needed, in Ubuntu.

Please share your results.
