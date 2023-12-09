---
title: "[HOWTO] Auto Re-Connect to dsl pppoe in Linux"
date: "2010-03-07"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "adsl"
  - "alpha"
  - "deluge"
  - "dsl"
  - "linux"
  - "lucid"
  - "lynx"
  - "poff"
  - "pon"
  - "pppoe"
  - "pppoeconf"
  - "reconnect"
  - "reconnecting"
  - "ubnt"
  - "ubuntu"
  - "worldlink"
---

I am using Ubuntu 10.04 Lucid Lynx Alpha. I have a dsl connection (WiZoom, Wireless via ubnt but wired to my PC) from Worldlink Pvt. Ltd., Nepal. I need to connect via pppoe. I occasionally keep my PC to download overnight while I sleep or even when I am away. It works well with torrents (with deluge as my torrent client, I haven't used transmission torrent client much) but sometimes it disconnects from the internet. So, I had to configure it to auto re-connect on disconnect. It should also connect on logon. Since network manager does not meet my requirements, I had to delete the DSL connection from my network manager (which I had configured to connect at logon). Then I would need to configure pppoe connection via pppoeconf. To do so, I bring up my terminal and type in:

sudo pppoeconf

After that I just answer a series of questions, which include my username and password. I leave all the other values to defaults as they work for me. If they don't work for you, you may need some tweaking. You should look for help elsewhere as I am not aware of other connection types/settings.  
Now, I can connect from my terminal using:

sudo pon dsl-provider

and disconnect using:

sudo poff -a

Now, I have verified that it works and am ready to move on. But disconnect does not disconnect me immediately. pppd does not terminate immediately after I use sudo poff -a so I had to write a small script that helps me disconnect immediately. To achieve that, I created a killpppd script and placed in /usr/local/sbin/. To do so, launch nautilus as root. To do so, press Alt+F2 and type in:

gksu nautilus /usr/local/sbin

Create a new text file and copy/paste or type in the following:

#!/bin/sh
#kill pppd brutally
for i in \`ps -eaf | grep "pppd" | tr -s " " | cut -f2 -d " "\`
do
sudo kill -9 ${i}
done

Then I made it executable (Right Click on the file>Properties>Permissions>Allow executing file as Programs). Now, we can just run

killpppd

from terminal and the pppd dies and connection is lost.  
I have created yet another file that tries to disconnect using poff and also kills pppd with killpppd. I have named it dcon and it contains the following text:

#!/bin/sh
sudo poff -a
sudo killpppd
sudo poff -a

Then I made it executable. This script first tries to disconnect gracefully and tries to kill pppd if that was not successful. I have made this like this because poff gives

/usr/bin/poff: No pppd is running.  None stopped.

if no pppd was running. So, I will get to know if pppd was running or not and if it did stop.  
Now, I need a connect script that only connects if the connection has been lost and does nothing if it has not. To achieve I use a small script by AT-HE and place it with name "connect" in /usr/local/sbin/. Here is the script:

#!/bin/sh
# adsl-reconnect.sh by AT-HE (at\_he hotmail) nov 2008. 
# Modified by \_khAttAm\_, March 2010

IFACE=ppp0
DOWN=dcon
UP="pon dsl-provider"
LOG=/var/log/dsl-reconnect.log

PTP=\`ifconfig $IFACE 2>&1|grep P-t-P|cut -d : -f 3|cut -d " " -f 1\`
RECV=\`ping -c 1 $PTP 2>&1|grep received|cut -d , -f 2|cut -d " " -f 2\`

if \[ "$RECV" != "1" \]
then
echo "connecting..."
echo ----- >>$LOG
date>>$LOG
$DOWN >>$LOG 2>&1
#wait for kill
sleep 3
echo "hopefully killed"
$UP >>$LOG 2>&1
fi

Then I made it executable. I have named this one connect and placed at /usr/local/sbin. The script uses our dcon script to disconnect and pon dsl-provider to connect. It checks if the IP of our server (placed at PTP variable) is ping-able. In that case, the connection has not terminated and it does nothing. However, if the IP of the server is not ping-able, it disconnects (which has probably already been disconnected but pppd may not have died, so we need to kill it otherwise the connection is made with interface ppp1, ppp2 and the script will not work) and then tries to connect. This must be run as root so I created another file named con in the same directory (usr/local/sbin/) with contents:

#!/bin/sh
sudo connect

Now, we can just run:

con

from the terminal.  
Now, we have four files in /usr/local/sbin namely con, dcon, connect and killpppd. They can all be used from the terminal. Basically, only con is required as it does everything. It connects to the internet if there is no connection and re-connects if connection has been lost.  
Now, I needed to run the "con" script periodically. I have chosen to run it every minute. I have used cron to do that. To do that, I ran

sudo crontab -e

. If you are running it for the first time, you will need to choose an editor. I just chose nano. Now, we need to write in the following line at the end of the file that opens in nano. You can use Shift+Insert to paste the following line:

\* \* \* \* \* /usr/local/sbin/con

. Remember, the line needs to be exactly the same with all the asterisks in place. Save it with Ctrl+O and exit using Ctrl+X and crontab should update the scheduled task. This makes cron run the script "con" every minute.

Hope this helps others too.

References:  
[http://kevin.vanzonneveld.net/techblog/article/schedule\_tasks\_on\_linux\_using\_crontab/](http://kevin.vanzonneveld.net/techblog/article/schedule_tasks_on_linux_using_crontab/)  
[http://geekhut.blogspot.com/2007/05/auto-reconnecting-lost-dsl-connection.html](http://geekhut.blogspot.com/2007/05/auto-reconnecting-lost-dsl-connection.html)
