---
title: "[HOWTO] Moving Gnote Notes to Tomboy and vice versa"
date: "2010-03-01"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "gnote"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "lynx"
  - "mono"
  - "note-taking"
  - "ppa"
  - "ubuntu"
---

I had moved to Gnote from Tomboy notes in my Ubuntu 10.04 Lucid Lynx Alpha because I wanted to free some space by removing mono (I don't play gbrainy and I do not have a photo collection in my PC :)).  
  
However, I have been facing crashes with Gnote recently. I updated to latest version of Gnote from the PPA with no success. I get the following error when I try to launch Gnote version 0.7.1-1ppalucid3 from the terminal:

progname=gnote; RGBA=on
(gnote:13961): GLib-GObject-WARNING \*\*: cannot register existing type \`gtkmm\_\_GtkTextBuffer'
(gnote:13961): GLib-GObject-WARNING \*\*: cannot register existing type \`gtkmm\_\_GtkTextBuffer'
(gnote:13961): GLib-GObject-WARNING \*\*: cannot retrieve class for invalid (unclassed) type \`'
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_object\_class\_find\_property: assertion \`G\_IS\_OBJECT\_CLASS (class)' failed
(gnote:13961): glibmm-WARNING \*\*: Glib::ConstructParams::ConstructParams(): object class "(null)" has no property named "tag\_table"
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_type\_class\_unref: assertion \`g\_class != NULL' failed
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_object\_newv: assertion \`G\_TYPE\_IS\_OBJECT (object\_type)' failed
(gnote:13961): Gtk-CRITICAL \*\*: gtk\_text\_buffer\_get\_tag\_table: assertion \`GTK\_IS\_TEXT\_BUFFER (buffer)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: cannot register existing type \`gtkmm\_\_GtkTextBuffer'
(gnote:13961): GLib-GObject-WARNING \*\*: cannot retrieve class for invalid (unclassed) type \`'
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_object\_class\_find\_property: assertion \`G\_IS\_OBJECT\_CLASS (class)' failed
(gnote:13961): glibmm-WARNING \*\*: Glib::ConstructParams::ConstructParams(): object class "(null)" has no property named "tag\_table"
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_type\_class\_unref: assertion \`g\_class != NULL' failed
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_object\_newv: assertion \`G\_TYPE\_IS\_OBJECT (object\_type)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_object\_ref: assertion \`G\_IS\_OBJECT (object)' failed
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_object\_unref: assertion \`G\_IS\_OBJECT (object)' failed
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_object\_ref: assertion \`G\_IS\_OBJECT (object)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): GLib-GObject-WARNING \*\*: invalid (NULL) pointer instance
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_signal\_connect\_data: assertion \`G\_TYPE\_CHECK\_INSTANCE (instance)' failed
(gnote:13961): Gtk-CRITICAL \*\*: gtk\_text\_buffer\_get\_end\_iter: assertion \`GTK\_IS\_TEXT\_BUFFER (buffer)' failed
(gnote:13961): Gtk-CRITICAL \*\*: gtk\_text\_buffer\_get\_start\_iter: assertion \`GTK\_IS\_TEXT\_BUFFER (buffer)' failed
(gnote:13961): Gtk-CRITICAL \*\*: gtk\_text\_buffer\_delete: assertion \`GTK\_IS\_TEXT\_BUFFER (buffer)' failed
(gnote:13961): Gtk-CRITICAL \*\*: gtk\_text\_buffer\_get\_start\_iter: assertion \`GTK\_IS\_TEXT\_BUFFER (buffer)' failed
(gnote:13961): GLib-GObject-CRITICAL \*\*: g\_object\_ref: assertion \`G\_IS\_OBJECT (object)' failed
zsh: segmentation fault (core dumped)  gnote

The bug has been filed [here](https://bugs.launchpad.net/ubuntu/+source/gnote/+bug/522372) but we are yet to see any improvements.

So I thought I should move back to Tomboy. I needed to get my notes that I created in Gnote back. To do that, I just had to copy the .note files from /home/MyUserName/.gnote to /home/MyUserName/.local/share/tomboy. After that, I had to quit and start Tomboy again and I can access the notes again with Tomboy.  
If I had to move these back again (i.e. from Tomboy to Gnote), I could delete the .gnote altogether (so that it asks for import) or copy .note from /home/MyUserName/.local/share/tomboy to /home/MyUserName/.gnote.

Let me know when Gnote starts working again.
