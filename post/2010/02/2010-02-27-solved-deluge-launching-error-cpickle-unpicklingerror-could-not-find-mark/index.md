---
title: "[SOLVED] Deluge Launching ERROR: \"cPickle.UnpicklingError: could not find MARK\""
date: "2010-02-27"
categories: 
  - "ubuntu-linux"
tags: 
  - "deluge"
  - "error"
  - "linux"
  - "ppa"
  - "state"
  - "torrent"
---

I just tried to launch deluge and got the following error:

progname=deluge; RGBA=on
Traceback (most recent call last):
  File "/usr/bin/deluge", line 9, in 
    load\_entry\_point('deluge==1.2.1', 'console\_scripts', 'deluge')()
  File "/usr/lib/pymodules/python2.6/deluge/main.py", line 121, in start\_ui
    UI(options, args, options.args)
  File "/usr/lib/pymodules/python2.6/deluge/ui/ui.py", line 128, in \_\_init\_\_
    ui = GtkUI(args)
  File "/usr/lib/pymodules/python2.6/deluge/ui/gtkui/gtkui.py", line 216, in \_\_init\_\_
    self.torrentdetails = TorrentDetails()
  File "/usr/lib/pymodules/python2.6/deluge/ui/gtkui/torrentdetails.py", line 116, in \_\_init\_\_
    state = self.load\_state()
  File "/usr/lib/pymodules/python2.6/deluge/ui/gtkui/torrentdetails.py", line 432, in load\_state
    state = cPickle.load(state\_file)
cPickle.UnpicklingError: could not find MARK

Deluge would just crash and would not show up at all.

I tried searching for a solution, but did not find any. I tried upgrading to the ppa version of deluge with no luck. Then I just removed all the .state (not to be mistaken with state directory) files (peers\_tab.state, files\_tab.state, torrentview.state, tabs.state, dht.state, session.state and any other file containing .state at the end) from /home/MyUserName/.config/deluge and was able to launch deluge again. You should not remove the state directory because you will lose the torrent list if you do.  
After that, you will be able to launch deluge. It is a good idea to recheck (Right click on a torrent file and select Force Recheck) all torrent files after you do this.

Hope this helps.
