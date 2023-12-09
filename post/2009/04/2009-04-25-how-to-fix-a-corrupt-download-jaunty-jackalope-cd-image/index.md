---
title: "How to fix a corrupt download (Jaunty Jackalope CD Image)"
date: "2009-04-25"
categories: 
  - "jaunty-ubuntu-linux-linux"
tags: 
  - "corrupt"
  - "download"
  - "iso"
  - "ktorrent"
  - "linux"
  - "torrent"
  - "web"
  - "windows"
---

I downloaded Ubuntu 9.04 Jaunty Jackalope ISO and discovered that the file was not downloaded properly. It was corrupt. It failed the md5 check and failed to install inside Sun VirtualBox.

I did not want to download the file again. I have a very poor internet connection. I had downloaded the file from http link with the help of wget.

The ISO was the size as specified in the site. I think this process works only if this holds true. Also, it needs to be available in the torrents. These hold true for the file I was trying to download.

I launched ktorrent and added the torrent to the file that I had downloaded. Then, when it started downloading, I quit ktorrent. Then I replaced the file it had created in the data directory with my corruput ISO. Launched ktorrent again and chose to check data. It then checked the file and quickly found that I needed to download only 16MB. I did and voila the file was fixed.

However, I used ktorrent, all torrent clients I have used (on Windows or Linux) have this feature of checking data. It might be called something other than "Check Data" in other torrent clients though.
