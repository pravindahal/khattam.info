---
title: "[SOLVED] DSL PPPoE not able to Connect in Ubuntu 9.10 Karmic Koala"
date: "2009-11-08"
categories: 
  - "karmic-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "device-not-managed"
  - "dsl"
  - "karmic"
  - "karmic-koala"
  - "knet"
  - "koala"
  - "kubuntu"
  - "linux"
  - "network-manager"
  - "ppa"
  - "pppoe"
  - "pppoeconf"
  - "ubuntu"
---

I used to connect to PPPoE connections in Kubuntu with knet. Recently, I moved to Ubuntu to find out that Network Manager was unable to connect to DSL. However, it can be achieved using pppoeconf or knet, I wanted to use Network Manager. I figured out that it was a problem with the final release itself when I visited the forums (I had installed Ubuntu Karmic Koala Alpha 4 and then upgraded as new packages came in).

The newer version of Network Manager did not have this problem but it is still not available on the main repos at the time of writing this post. There is a ppa however, which helped me. It contained updated version of the package which is https://launchpad.net/~network-manager/+archive/trunk.

You need to connect using pppoeconf to download latest updates. Here is how you do it in the terminal:  
sudo pppoeconf  
Now, follow the instructions and put in your connection details. Leave the default values if you are not sure. However, don't forget to put in your username and password.  
To connect, simply use:  
sudo pon dsl-provider  
To disconnect, use  
sudo poff -a

Now, once you are connected, open up synaptic and in Settings>Repositories>Other Software Tab, click on Add and then type in the following in the apt line:  
deb http://ppa.launchpad.net/network-manager/trunk/ubuntu karmic main  
Again, click on Add and type in the following  
deb-src http://ppa.launchpad.net/network-manager/trunk/ubuntu karmic main

Now, close Software Sources box and click on Reload in Synaptic. Now, mark all upgrades and Apply and when the updates are installed, newer version of Network Manager is installed too and you must be able to connect, unless of course there are new bugs which do not let you connect.

Hope this was helpful.

UPDATE - DEC 3 2009: If you get a "device not managed" in Network Manager, you will need to do the following:  
Open /etc/network/interfaces as root and comment or remove all the lines except the two with lo. To do so, Alt+F2 and type in gksu gedit /etc/network/interfaces and then add # in front of all other lines except ones containing lo. Then restart and your Network Manager should work fine. This happens if you have configured your connection with pppoeconf.
