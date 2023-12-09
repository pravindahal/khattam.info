---
title: "[SOLVED] vnstat: \"Zero database found, exiting\""
date: "2010-11-09"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "linux"
  - "vnstat"
---

I am using Ubuntu 10.10 Maverick Meerkat and I installed vnstat v1.10-1 from the terminal using apt-get:

sudo apt-get install vnstat

The installation ended with an error:

> \* Starting vnStat daemon vnstatd Zero database found, exiting. \[fail\]

When I tried to monitor my traffic using the following command:

vnstat -m -i eth0

I got the following error:

> Error: Unable to read database "/var/lib/vnstat/eth0".

Then I ran vnstat from the command line and got the following:

> No database found, nothing to do. Use --help for help. A new database can be created with the following command:
> 
> vnstat -u -i eth0 Replace 'eth0' with the interface that should be monitored. The following interfaces are currently available:
> 
> lo eth0 vboxnet0

Since my computer is using eth0, I created a database for eth0 using the following command:

sudo vnstat -u -i eth0

I got the following output:

> Error: Unable to read database "/var/lib/vnstat/eth0".
> 
> Info: -> A new database has been created.

Now, I am able to monitor my Internet traffic using vnstat.
