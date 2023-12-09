---
title: "[SOLVED] Unable to launch gtk-recordmydesktop advanced preferences"
date: "2010-12-09"
tags: 
  - "gtk-recordmydesktop"
  - "jackd"
  - "linux"
  - "recordmydesktop"
---

When I tried to launch the Advanced options in gtk-recordmydesktop, a gtk front end to recordmydesktop which enables Desktop recording in Linux, I got no GUI error but when I ran the same from the terminal, I could see the following error:

> (stdin,stdout,stderr)=os.popen3(\['jack\_lsp'\],'t') Traceback (most recent call last): File "/usr/lib/pymodules/python2.6/recordMyDesktop/rmdSimple.py", line 192, in advanced self.options=pW.prefsWidget(self,self.values,self.optionsOpen) File "/usr/lib/pymodules/python2.6/recordMyDesktop/rmdPrefsWidget.py", line 410, in \_\_init\_\_ self.\_\_runJackLSP\_\_() File "/usr/lib/pymodules/python2.6/recordMyDesktop/rmdPrefsWidget.py", line 331, in \_\_runJackLSP\_\_ (stdin,stdout,stderr)=os.popen3(\['jack\_lsp'\],'t') File "/usr/lib/python2.6/os.py", line 695, in popen3 stderr=PIPE, close\_fds=True) File "/usr/lib/python2.6/subprocess.py", line 623, in \_\_init\_\_ errread, errwrite) File "/usr/lib/python2.6/subprocess.py", line 1141, in \_execute\_child raise child\_exception OSError: \[Errno 2\] No such file or directory

It seemed it had something to do with jack audio server so I installed jackd package and the error was gone.
