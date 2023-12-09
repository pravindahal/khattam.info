---
title: "[SOLVED] Disable Note of the Day Add-in Permanently in Gnote"
date: "2010-10-03"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "add-ins"
  - "gnote"
  - "linux"
  - "note-of-the-day"
  - "tomboy"
---

I have been using gnote for quite some time now instead of Tomboy notes in my Ubuntu 10.10 Maverick Meerkat. Gnote currently does not disable add-ins permanently. However someone may find the Note of the Day add-in useful, it annoys me and I tried to disable it in Preferences>Add-ins, even in the latest stable version 7.2. However, that did not work. So, to disable it, I decided to move the plugin file where gnote would not load from.

To do that, you can use the following commands. It should work for any version that you have.

sudo mkdir "/usr/lib/gnote/addins/\`gnote --version 2>&1| cut -d\\  -f2\`/disabled"
sudo mv "/usr/lib/gnote/addins/\`gnote --version 2>&1| cut -d\\  -f2\`/libnoteoftheday.so" "/usr/lib/gnote/addins/\`gnote --version 2>&1| cut -d\\  -f2\`/disabled/" 
killall gnote

When you start it again, the note of the day should be gone.

If you want to re-enable it again, just use the command:

sudo mv "/usr/lib/gnote/addins/\`gnote --version 2>&1| cut -d\\  -f2\`/disabled/libnoteoftheday.so" "/usr/lib/gnote/addins/\`gnote --version 2>&1| cut -d\\  -f2\`/" 
killall gnote

When you launch it again, the plugin should be enabled again.

Hope this helps.
