---
title: "[SOLVED] Frequent corrupt HTTP downloads on Windows"
date: "2013-12-30"
tags: 
  - "windows"
---

**Note:** If you are just looking for the final solution, skip to the last paragraph.

On my new Windows 7 64-bit installation, I started getting frequent corrupt downloads when files were downloaded via HTTP. First, I thought my download manager (Free Download Manager) was buggy. However, I got corrupt downloads when downloading via Firefox too. I noticed it happening even with third party web installers and even Windows update (with error "WindowsUpdate\_80246002" "WindowsUpdate\_dt000"). However, downloads via torrent client were fine. So were downloads over SSH Proxy Forwarded tunnel and downloads over HTTPS.

These symptoms could be caused by various reasons. I suspected malware infection but latest updated version of Bitdefender Free did not detect any. Neither did Malwarebytes. Also, the bug was reproduced inside an isolated Virtual Machine with a different OS too using NAT. So, malware infection was ruled out.

Another reason this could happen is because of faulty networking hardware or buggy driver. Bittorrent has integrity checks on application layer so it automatically repairs corruption due to faulty hardware and drivers. However, it was strange that downloads over HTTPS and SSH VPN connections were not buggy.

The network adapter I was having this problem with is Intel® Centrino® Wireless-N 1030 and driver version is 14.3.0.6. So, I decided to try to update the driver. I ran the [Intel® Driver Update Utility](http://www.intel.com/p/en_US/support/detect "Intel® Driver Update Utility") and found that a newer version of the driver (application version 16.7.0, driver version 15.9.2.1) is available for download. So, I downloaded it using the SSH Proxy Forwarded tunnel (you could download it in a different computer or [setup a tunnel](http://www.digitalmobile.in/community/threads/free-shell-accounts-with-unlimited-ssh-tunneling.5882/ "setup SSH tunnel") and download using it) and installed it. However, updating drivers didn't help either.

So I suspected that since connections over secure connections were fine, something intercepting non-secure connections could be a problem. The first suspect was Bitdefender Antivirus. I removed it and rebooted. The problem no longer existed. All the downloads following Bitdefender uninstall were fine. I searched for this and found that [other users were having the same problem too](http://forum.bitdefender.com/index.php?showtopic=40187 "Bitdefender corrupts downloads") and it was not a Bitdefender bug but a Windows bug which also affects other security suites that monitor HTTP traffic.

The solution is to install Windows hotfix KB2735855. Download it [here for 32-bit Windows 7](http://www.microsoft.com/en-us/download/details.aspx?id=34637) and [here for 64-bit Windows 7](http://www.microsoft.com/en-us/download/details.aspx?id=34629). According to [Microsoft's article regarding this bug](http://support.microsoft.com/kb/2735855#appliesto), this bug only applies to Windows 7, Windows Server 2008 R2 and Windows Web Server 2008 R2.
