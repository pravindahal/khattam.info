---
title: "[HOWTO] Setup a Minimal Ubuntu LAMP server (with ssh server)"
date: "2010-12-11"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "apache"
  - "apache2"
  - "linux"
  - "mysql"
  - "openssh"
  - "php"
  - "virtualbox"
---

In this article, I will describe how I went about to install the bare minimum LAMP server using Ubuntu Minimal installation iso. I downloaded Maverick Meerkat version of Minimal CD image from the [Minimal CD Image Download Page](https://help.ubuntu.com/community/Installation/MinimalCD). You can use the server ISO but you may end up with unwanted packages and you will need to download the whole ~700 MB ISO to start, while Minimal CD is just ~13MB. Also, since the Minimal CD downloads the latest packages from the repos during installation, you need not update immediately further saving data volume.

I am installing inside VirtualBox 4.0 Beta. However, these instructions should apply to other Virtualization solutions or even a physical machine.

Boot into the computer with the CD Image (either burn it to business card CD-ROM or normal CD-ROM if using Physical Machine otherwise just mount inside VirtualBox) and follow the on-screen instructions and select appropriate settings that apply to you. At the last stages of the installation, you will be asked to select packages, select none. It will complete installing the basic packages and install Grub and reboot.

After reboot, you will be able to login. After logging in, enter the following command:

sudo apt-get install mysql-server phpmyadmin ssh

The above command should install the following components: openssh-server apache2 mysql-server mysql-client php phpmyadmin

At the end of the installation, just select appropriate settings and setup passwords.

Now, when you launch a browser in another machine, you can open http://IP.OF.THE.MACHINE and you will see that system is ready, if everything went right. The installed size is less than 1GB (excluding swap).

Hope this helps.
