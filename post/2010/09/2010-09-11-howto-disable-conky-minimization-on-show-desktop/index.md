---
title: "[HOWTO] Disable conky minimization on Show Desktop"
date: "2010-09-11"
tags: 
  - "ccsm"
  - "compiz"
  - "compiz-config-settings-manager"
  - "conky"
  - "linux"
  - "scale"
---

If you have conky installed, then by default when you click on Show Desktop icon on your panel, conky also gets minimized. You can bring it back by clicking it again, but that does not work if you open another window or selectively maximize/restore a window(s). Also, when you click on the Desktop after activating scale, then conky is lost. In both of these cases, the conky process keeps running, however it cannot be brought back. You must terminate it and run conky again.

However, if you just disable "Hide Skip Taskbar Windows" under General Settings in Compiz-config-settings-manager (ccsm), then conky will not be minimized if you press Show Desktop icon and it will not get lost if you click the Desktop after scale plugin is activated.

Hope this helps.
