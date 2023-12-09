---
title: "[SOLVED] Compiz text input problem in Ubuntu 11.04 Natty Narwhal Alpha 1"
date: "2010-12-04"
categories: 
  - "natty-narwhal"
  - "ubuntu-linux"
tags: 
  - "compiz"
  - "linux"
---

If you are using Ubuntu 11.04 Natty Narwhal Alpha, you may face compiz crashes. To recover from compiz crash, you can do a

compiz --replace

, but sometimes, you are not able to input text any more so doing that is not possible. Then, all you can do is restart the system. However, compiz can be restarted from other terminals. If you encounter a crash and are no longer able to input text, press Ctrl+Alt+F1 and login. Now, type in the following:

DISPLAY=:0.0 compiz --replace

Now, when you press Ctrl+Alt+F7, you will see that compiz has restarted and you can type text again. If some components (like unity) fail to load, bring up the terminal by pressing Ctrl+Alt+T and type in

compiz --replace

to load compiz again.

If it does not work, login to the terminal (Ctrl+Alt+F1-F6) and remove the compiz settings directory from your home directory. Here is how you do that:

cd
mv .compiz-1 compiz-old

Now, restart compiz:

DISPLAY=:0.0 compiz --replace

Hope this helps.
