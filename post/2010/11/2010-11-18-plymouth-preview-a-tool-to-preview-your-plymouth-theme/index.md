---
title: "plymouth-preview, a tool to preview your plymouth theme"
date: "2010-11-18"
categories: 
  - "debian-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "plymouth"
  - "plymouth-preview"
---

I have written a small shell script to preview plymouth themes. I have successfully tested it in Ubuntu 10.10 Maverick Meerkat and Debian Squeeze Testing. It should also work with other Linux distros. Please make sure you have installed the package plymouth-x11 (or equivalent) before using this script.

In Debian, you can install plymouth-x11 by executing the following command as root:

apt-get install plymouth-x11

For Ubuntu, use sudo in the beginning of the command.

Here is the script:

#!/bin/bash

## Preview Plymouth Splash ##
##      by \_khAttAm\_       ##
##    www.khattam.info     ##
##    License: GPL v3      ##

chk\_root () {

  if \[ ! $( id -u ) -eq 0 \]; then
    echo Must be run as root
    exit
  fi

}

chk\_root

DURATION=$1

if \[ $# -ne 1 \]; then
	DURATION=5
fi

plymouthd; plymouth --show-splash ; for ((I=0; I<$DURATION; I++)); do plymouth --update=test$I ; sleep 1; done; plymouth quit

Save the above script somewhere and run as root.

It accepts one command line argument, which specifies the number of seconds you wish to display the splash. The default value is 5, but you can change the script to alter the default value.

References: [http://brej.org/blog/?p=158](http://brej.org/blog/?p=158)
