---
title: "[SOLVED] Torrent stopped downloading although there are enough seeds and connections"
date: "2010-09-11"
tags: 
  - "azureus"
  - "deluge"
  - "linux"
  - "seeds"
  - "stuck"
  - "torrent"
  - "trackers"
  - "vuze"
  - "web"
---

I was downloading a large file from torrent and it stopped at 63%.  I was using deluge as my torrent client. Since there were enough seeds and enough connections were being made for the torrent to get going but it did not, I thought it was a deluge specific issue, so I got rid of it and installed Vuze (also called azureus) and moved the torrent to it. The way you do that is just start the same torrent in vuze, stop it and copy the files you had downloaded via older torrent client replacing the files being downloaded via vuze, then right click the torrent in vuze and then click "Force Recheck". But to my surprise, the torrent still got stuck just like in deluge.

Then I right clicked on the torrent and selected Show Details. In the Sources tab, I saw a lot of trackers were unreachable or timeout was occurring while attempting to connect to them. So, since there were many trackers that were online, I decided to remove those faulty trackers. To do so, I went back to the torrent listing, right clicked on the torrent and then navigated to Advanced>Tracker/Torrent>Edit Tracker URL(s) and then removed all those except those that were online.

After that, the torrent started downloading again. Hope this helps others who are experiencing similar problems.
