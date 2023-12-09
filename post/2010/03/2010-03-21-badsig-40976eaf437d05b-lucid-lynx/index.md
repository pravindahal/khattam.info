---
title: "[SOLVED] \"BADSIG 40976EAF437D05B5\" when reloading package lists in Synaptic/apt/update-manager in Ubuntu 10.04 Lucid Lynx"
date: "2010-03-21"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "10-04"
  - "40976eaf437d05b"
  - "badsig"
  - "linux"
  - "lucid"
  - "lucid-lynx"
  - "synaptic"
  - "ubuntu"
  - "update-manager"
---

I am using Ubuntu 10.04 Lucid Lynx Beta 1 and got the following set of warnings while updating my package lists

W: A error occurred during the signature verification. The repository is not updated and the previous index files will be used.GPG error: http://archive.ubuntu.com lucid Release: The following signatures were invalid: BADSIG 40976EAF437D05B5 Ubuntu Archive Automatic Signing Key 

W: Failed to fetch http://archive.ubuntu.com/ubuntu/dists/lucid/Release  

W: Some index files failed to download, they have been ignored, or old ones used instead.

This was preventing the package list updates and hence preventing package updates. I don't know what caused this or when exactly I started to get these, but I guess it was after I changed my packages server from np.archive.ubuntu.com to archive.ubuntu.com.

Anyways, I managed to fix it by (re)moving all the old package lists and updating again. This can be summed up in the following three lines of terminal commands:

sudo mv /var/lib/apt/lists /var/lib/apt/lists.old
sudo mkdir -p /var/lib/apt/lists/partial
sudo apt-get update

This did it for me. Hope it does it for you too.
