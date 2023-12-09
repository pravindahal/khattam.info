---
title: "Ubuntu to become a rolling release distro"
date: "2010-11-24"
categories: 
  - "debian-linux"
  - "lmde"
  - "ubuntu-linux"
tags: 
  - "debian"
  - "linux"
  - "linux-mint"
  - "lmde-2"
  - "rolling-release"
  - "ubuntu"
---

**UPDATE:** Rick Spencer, Ubuntu Desktop Development Team Lead, wrote in his blog:

> Ubuntu is not changing to a rolling release. We are confident that our customers, partners, and the FLOSS ecosystem are well served by our current release cadence. What the article was probably referring to was the possibility of making it easier for developers to use cutting edge versions of certain software packages on Ubuntu.This is a wide-ranging project that we will continue to pursue through our normal planning processes.

[The Register](http://www.theregister.co.uk/2010/11/23/darily_ubuntu_updates/), [OMG Ubuntu](http://www.omgubuntu.co.uk/2010/11/ubuntu-to-become-a-rolling-release-distro), [Webupd8](http://www.webupd8.org/2010/11/ubuntu-becoming-rolling-release-distro.html), [Ostatic](http://ostatic.com/blog/ubuntu-to-become-a-rolling-release) and a few other sites that feature articles about Ubuntu have recently posted articles regarding Ubuntu becoming a rolling release distro. However, it has not been officially announced, there has been quite a buzz.

Ubuntu has started as a release-cycle-based distro, in that a new version is rolled out every 6 months (and not daily). However, for a desktop based distro, it is not unrealistic to think the possibilities of a rolling release type distro considering the fact that it has been difficult to get the latest and greatest software in old Ubuntu installations. Currently, that either has to be done manually or via PPAs or it is not even possible in some cases due to [dependency hell](//ftp.debian.org/debian testing main contrib non-free). Linux Mint has taken a step recently to explore this possibilities by launching Linux Mint Debian Edition, which is a rolling release type distro based on Debian testing.

When I used Ubuntu, I used to try and get the latest software by using daily builds or alpha/beta releases with a lot of PPAs, which made it almost like a rolling release - updated but unstable linux installation with a lot of manual work involved, just for maintaining the OS and of course the need to download latest versions of applications daily. This is what I have to do with Debian anyways, so I recently moved to Debian testing to see how it works.

Making Ubuntu a completely rolling release based distribution would make it either unstable or it will have to give up on latest software anyways and only let tested and stable software for upgrades. Both of these will mean that Ubuntu will either be unsuitable for Enterprise use or stale for Desktop use.

One option will be to start an unstable branch for Ubuntu which will be a rolling release and will contain the latest and greatest software and another testing branch, also a rolling one, which will have software which has been passed from unstable but still might have issues and a different branch for Enterprise use. Enterprises will also need that their software will not be changed on updates. So, they will need fixed release cycles for Enterprise Editions anyways. So, Canonical could decide to release Ubuntu stable versions every few years or so. Debian does this in a similar way. They could of course choose different names for the branches; something like Ubuntu Current, Ubuntu Standard and Ubuntu Enterprise version X (codename Y). They could also use animal names for the same, as they currently do.

However, I think there are better ways to do things so that the users are given a choice. That can be done by releasing standard editions at longer intervals. The base system shall be released every few years (like they release LTS) and it will have a standard softwares suitable for Enterprise use.  Ubuntu-base could consist of linux kernel, drivers and other base packages which will not get upgrades but only critical fixes. All other softwares will have their own PPA like repositories, which can either be maintained by Canonical or by software developers themselves. When a newer version upgrade is available for a software, users can be prompted to either stay with the current version or upgrade to the newer version. If a user chooses to stay with the current version, the users repositories for the software remains the same and the user will continue getting minor updates and bug fixes for the same unless the support ends. If a user chooses to upgrade, the repository for that particular software is changed and the older software is replaced with the newer one (with a choice to either remove the older version or to keep it). If the user wants development version of the package, the user may manually choose to upgrade to development version. Also, the user must be able to downgrade to the previous version without any problems.

This approach will fulfill the users needs. On a Enterprise front, the administrator may choose not to upgrade to the latest version, for stability and consistency. However, a casual home user may want to explore the latest version and may install it. A developer or a geek may choose to install development version too.

There might however be problems with this approach too. The problem is when it comes to libraries. If an application depends on one version of a library and the other depends on another version of the same, they may not co-exist. However, a workaround is to name the libraries with version names. That way, multiple versions of the same library can be installed. If this is allowed, multiple version of the same application can be installed too.

All of this is already possible with apt, so it can be done if they wish to. However, it will require a complete overhaul, it could be worth it.
