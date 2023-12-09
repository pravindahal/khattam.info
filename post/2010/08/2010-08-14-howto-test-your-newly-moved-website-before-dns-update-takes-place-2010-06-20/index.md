---
title: "[HOWTO] Test your newly moved website before DNS update takes place"
date: "2010-08-14"
tags: 
  - "dns"
  - "dns-update"
  - "linux"
  - "web"
  - "windows"
---

I recently moved some of my websites to new VPS. That requires DNS changes and I updated DNS on my domain registrar. I was not sure how my sites would adapt to new host and decided to test them. To do so, I changed hosts file such that the browser is pointed directly to new host instead of querying DNS server for the IP. Then I could browse my new site just fine after a few refreshes.

Lets take for example, the IP of your new hosting provider is 74.54.99.241. You can find this in the Control Panel of the new host or by asking the support staff. Then, just open up your hosts file. On Linux systems, you will find your hosts file in /etc/hosts. You will need to open it in a text editor as root. On Windows XP, you can simply open up C:\\Windows\\System32\\drivers\\etc\\hosts (assuming you have Windows installed in C:) in notepad. On Windows Vista/7, you will need to open notepad as Administrator (from the start menu, search for notepad and then Right Click>Run as Administrator) and then use File>Open to open C:\\Windows\\System32\\drivers\\etc\\hosts. Now, add the following lines to your hosts file:

yoursite.com          74.54.99.241
www.yoursite.com   74.54.99.241

**Note:** Use your IP, not this.

Then restart your browser. You can try refreshing but it may not work with some browsers. Now, when you open yoursite.com or www.yoursite.com, the one in your new hosting provider will load.

Hope this helps.

Thanks to [Deepak Mittal](http://www.absolutelytech.com/) for this tip.
