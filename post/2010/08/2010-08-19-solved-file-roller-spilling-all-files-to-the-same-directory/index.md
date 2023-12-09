---
title: "[SOLVED] File-roller (Archive Manager) spilling all files to the same directory"
date: "2010-08-19"
categories: 
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "archive-manager"
  - "file-roller"
  - "gconf-editor"
  - "linux"
---

I am using Ubuntu 10.10 Maverick Meerkat. I don't remember how or when it happened, but I noticed that while "Right Click On Archive>Extract Here" was working well, "Open Archive File in File-roller a.k.a. Archive Manager (double click)>Right Click on an item>Extract..." was not behaving as expected. It was not recreating the directory structure and spilling all the files to the same target directory.

To fix this, you can either clear all the settings of file-roller so that when you start file-roller next time, it creates all the default settings, or you can edit the configuration manually using gconf editor.

**Method I** The first method can be accomplished by typing the following in the terminal:

mv ~/.gconf/apps/file-roller/ ~/.gconf/apps/file-roller.bak/

**Method II** The second method is safer since it keeps all other file-roller settings. But you should worry about settings only if you have edited the settings. If you have not, 1st method is easier. If you want to just change what is required, then launch gconf-editor (Alt+F2>gconf-editor) and then navigate to /apps/file-roller/dialogs/extract in the right hand pane. Now, look for a boolean key recreate\_folders. If it is not there, create it. Then change the value to true (checked).

After following one of these methods, close all instances of file-roller and start it again for changes to take effect.
