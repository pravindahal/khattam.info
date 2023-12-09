---
title: "[SOLVED] Error: 0x800F0A12 while installing Windows 7 Service Pack 1"
date: "2011-06-01"
tags: 
  - "disk-management"
  - "diskmgmt-msc"
  - "grub"
  - "windows"
---

When trying to update Windows 7 Ultimate to Service Pack 1 using Windows Update, I got error: 0x800F0A12. I have two hard disks of which one has Fedora 15 and the other has Windows 7, the one with Fedora 15 had Grub installed. I disconnected the other hard disk and tried it again and the issue was resolved. If you have single hard disk with some other OS installed, you may face similar error which is a little more difficult to solve. Before performing this, make sure to back up your important data and have recovery tools handy. Please proceed at your own risk.

To solve the issue, you have to set the partition with Windows 7 as active using Disk Management (Win+R: diskmgmt.msc) by right clicking the partition and selecting "Mark Partition as Active". After the update has been installed, make sure to set your other partition which has the boot loader as active.
