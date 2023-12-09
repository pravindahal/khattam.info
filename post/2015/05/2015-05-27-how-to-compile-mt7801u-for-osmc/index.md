---
title: "How to compile mt7801u for OSMC"
date: "2015-05-27"
categories: 
  - "debian-linux"
  - "osmc"
  - "raspberry-pi"
tags: 
  - "linux"
---

_**Note:** This may already be fixed with latest version of OSMC._ _**Note:** My device was not detected in Raspberry Pi Model B (older model) because apparently, it can't provide enough power to it. It does work with powered USB hub though._

I have a USB Network Hub (WiFi 360) from a Chinese manufacturer. It is detected as "Bus 001 Device 005: ID 148f:760b Ralink Technology, Corp.". To get it working, I had to go through the following:

First, I sshed into the machine (you can do it with ssh command from \*nix machines or Putty tool from Windows machine). The default credentials are osmc/osmc.

Then I installed usbutils to use lsusb.

sudo apt-get update
sudo apt-get upgrade
sudo apt-get -y install usbutils

Then I used lsusb to confirm that the USB WiFi Dongle is connected properly. I also ran ifconfig to check if it is already detected.

Then I installed git, gcc, make and build-essential:

sudo apt-get install git gcc make build-essential -y

Then I installed kernel headers:

set -- $(cat /proc/cmdline) && for x in "$@"; do case "$x" in osmcdev=\*) sudo apt-get update && sudo apt-get install -y "${x#osmcdev=}-headers-$(uname -r)"; ;; esac; done

And then kernel source (which is ~100M so might take some time depending on your internet connection):

set -- $(cat /proc/cmdline) && for x in "$@"; do case "$x" in osmcdev=\*) sudo apt-get update && sudo apt-get install -y "${x#osmcdev=}-source-$(uname -r)"; ;; esac; done

Then I fetched the source for driver:

cd
git clone https://github.com/porjo/mt7601.git

Then I prepared kernel source for compilation:

cd /usr/src
set -- $(cat /proc/cmdline) && for x in "$@"; do case "$x" in osmcdev=\*) sudo tar xjvf /usr/src/"${x#osmcdev=}-source-$(uname -r).tar.bz2"; ;; esac; done
set -- $(cat /proc/cmdline) && for x in "$@"; do case "$x" in osmcdev=\*) cd /usr/src/"${x#osmcdev=}-source-$(uname -r)"; ;; esac; done
sudo make mrproper
set -- $(cat /proc/cmdline) && for x in "$@"; do case "$x" in osmcdev=\*) sudo cp /boot/config-"$(uname -r)" .config; ;; esac; done
sudo cp .config .config.org
sudo make modules\_prepare
set -- $(cat /proc/cmdline) && for x in "$@"; do case "$x" in osmcdev=\*) sudo cp /usr/src/"${x#osmcdev=}-headers-$(uname -r)"/Module.symvers ./; ;; esac; done
set -- $(cat /proc/cmdline) && for x in "$@"; do case "$x" in osmcdev=\*) sudo ln -s /usr/src/"${x#osmcdev=}-source-$(uname -r)"/ /lib/modules/"$(uname -r)"/build; ;; esac; done

Then I built the driver:

cd
cd mt7601/src
make

It took some time (around 20 minutes on a Raspberry Pi 1 B+) and a lot of warnings were shown but apparently they were safe to ignore.

Finally, I installed it:

sudo mkdir -p /etc/Wireless/RT2870STA
sudo cp RT2870STA.dat /etc/Wireless/RT2870STA
sudo cp os/linux/mt7601Usta.ko /lib/modules/"$(uname -r)"/kernel/drivers/net/wireless/

Then I rebooted:

sudo reboot; exit

After reboot, I reconnected ssh and I could see the new interface ra1 when running ifconfig:

ifconfig

If you update your system and if it again stops detecting the device, you should follow the same instructions again.

Sources: [https://github.com/Shareed2k/osmc\_mt7601\_driver](https://github.com/Shareed2k/osmc_mt7601_driver) [https://osmc.tv/help/wiki/kernel-sources](https://osmc.tv/help/wiki/kernel-sources)
