---
title: "[HOWTO] Enable \"delete\" key in Nautilus 3 (Fedora 15)"
date: "2011-06-01"
tags: 
  - "delete"
  - "fedora"
  - "linux"
  - "move-to-trash"
  - "nautilus"
  - "nautilus-3"
---

By default, the keyboard short cut for "Move to Trash" is Ctrl+Delete in Nautilus 3 in Fedora 15. To set Delete as short cut for Move to Trash operation, follow the steps below.

Launch the terminal and execute the following to enable short cut editing:

gsettings set org.gnome.desktop.interface can-change-accels true

Now, open (Nautilus) File Manager and select a file. Now, click on Edit menu and take your mouse over to "Move to Trash". With mouse over this item, press "Delete" key two times. Now, you will see the short cut has been set as the key for "Move to Trash".

In terminal, type in the following to disable short cut editing:

gsettings set org.gnome.desktop.interface can-change-accels false

Hope this helps.
