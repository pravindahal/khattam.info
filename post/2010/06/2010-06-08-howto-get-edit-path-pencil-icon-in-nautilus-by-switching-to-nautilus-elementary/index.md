---
title: "[HOWTO] Get Edit Path Pencil Icon in Nautilus by Switching to Nautilus Elementary"
date: "2010-06-08"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "karmic"
  - "karmic-koala"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "maverick"
  - "maverick-meerkat"
  - "nautilus"
  - "nautilus-elementary"
  - "pencil-icon"
---

Nautilus has breadcrumbs navigation. When you have a location you want to navigate to in a clipboard (copied from terminal or say a file), and if you wish to navigate to that location, you need to open up the run dialog (Alt+F2) and paste the location there or press Ctrl+L in any nautilus window and paste the location there. Both of these require keyboard. When there was Edit (Pencil) icon in Nautilus in some earlier versions, you could just press it and paste the location right there. But since it is removed now, it is not possible.

Nautilus elementary is a fork of Nautilus File Manager which claims to patched for simplicity. It now has a toolbar editor and you can easily add pencil icon to your toolbar using this feature.

It is currently available for Karmic and Lucid. To install it, open up Synaptic Package Manager (Alt+F2>gksu synaptic) and navigate to Settings>Repositories>Other Software and Add ppa:am-monkeyd/nautilus-elementary-ppa. If you are using Maverick, it is not available now, but you can use the Lucid PPA just by editing the entry (after adding, select it and choose Edit) and it should work fine. Now, close the dialogs and Reload in Synaptic. Mark All Upgrades and install it. You will need to logout and log in (or simply kill nautilus.. Alt+F2>killall nautilus) for changes to take effect. Now, to get the pencil icons or add/remove/move other toolbar elements, navigate to Edit>Customize Toolbar.

Hope this helps.
