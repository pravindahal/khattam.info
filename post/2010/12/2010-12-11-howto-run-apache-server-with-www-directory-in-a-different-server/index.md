---
title: "[HOWTO] Run apache server with www directory in a different server"
date: "2010-12-11"
categories: 
  - "debian-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "apache"
  - "ifdown"
  - "ifup"
  - "linux"
  - "ssh"
  - "sshfs"
  - "web-server"
---

This is an experiment in which I wanted to see if it is possible to run apache on one server and have www directory in a different server (physical or virtual). I don't know the possible benefits of such a system or a scenario where this could be helpful, neither am I aware of different ways to achieve the same. But I tried it and am posting the results anyways. :D

## The Problem

I am assuming a hypothetical problem where a user wants to run apache server in one machine and have the www directory in a different system. Let's call the machine with apache2 installed as Web Server (WS) and for the system with www directory, lets use the name File Server (FS).

## The Plan

The plan is to mount the www directory of FS to a directory of WS with sshfs and configure apache in WS to use that sshfs directory.

## Working Environment

I am using my Debian Testing system as FS and Ubuntu 10.10 Maverick Meerkat inside VirtualBox virtual machine (using Bridged connection) as WS which has apache installed. I have openssh server installed in FS and openssh client and sshfs installed in WS.

## Plan Execution

**Apache Configuration** First, lets login to WS and configure apache to use a directory in normal user's home directory (/home/ws\_username/www) by editing /etc/apache2/sites/available/default. The DocumentRoot is set to /home/ws\_username/www and a Directory is set to /home/ws\_username/www/ (no virtual hosts, however, using virtual hosts should not be much different either). Stop apache server for now:

sudo service apache2 stop

**Testing SSH connection from WS to FS** Now, connect from WS to FS using:

ssh fs\_username@fs\_ip\_or\_domain\_name

and verify connection is OK. Add to known hosts (if connecting for the first time). Then type

exit

to disconnect. **Setting up SSH connection without password** If not already created, create a ssh key pair using the command in WS:

ssh-keygen

That should ask you where to store the rsa public key (it is stored by default in /home/ws\_username/.ssh/id\_rsa/ as /home/ws\_username/.ssh/id\_rsa/id\_rsa.pub). Use a blank password. If you use a password, you may have to use ssh-agent for authentication later (not covered in this article). Now, transfer the pub key to FS using scp.

scp ~/.ssh/id\_rsa/id\_rsa.pub fs\_username@fs\_ip\_or\_domain\_name:

Then, ssh to FS:

ssh fs\_username@fs\_ip\_or\_domain\_name

Now, add the rsa keys copied from WS earlier to authorized\_keys file in FS:

cat id\_rsa.pub >>~/.ssh/authroized\_keys
rm id\_rsa.pub

Exit to disconnect and drop to WS shell. **Testing SSH connection from WS to FS without password** If you followed the instructions correctly, you will be able to connect to FS from WS without password when you use SSH.

ssh fs\_username@fs\_ip\_or\_domain\_name

Exit to disconnect:

exit

**Manually mount the www directory in FS to WS using sshfs** Now, test if sshfs is able to mount the directory from FS to WS. Let us assume the www directory is in /home/fs\_username/webprojects and is properly readable/writable (as required) by fs\_username. First, allow the user to mount by adding the ws\_username to fuse group by running the following command:

sudo gpasswd -a ws\_username fuse

Mount the directory to /home/ws\_username/www using sshfs:

sshfs -o idmap=ws\_username fs\_username@fs\_ip\_or\_domain\_name:/home/fs\_username/webprojects  /home/ws\_user/www

Confirm successful mounting by listing the contents:

ls /home/ws\_username/www

Unmount when done testing:

fusermount -u /home/ws\_username/www

**Setup /etc/fstab to be able to mount and unmount using mount and unmount instead** Open up /etc/fstab and add the following line:

sshfs#fs\_username@fs\_ip\_or\_domain\_name:/home/fs\_username/webprojects /home/ws\_username/www fuse fsname=sshfs#fs\_username@fs\_ip\_or\_domain\_name:/home/fs\_username/webprojects,users,allow\_other,uid=1000,gid=104,comment=sshfs,exec,reconnect,transform\_symlinks,BatchMode=yes,noauto 0 0

Don't use uid and gid values as they appear above. Instead, get those values by running the following command in terminal:

id

Make sure to use the uid and gid (of fuse group) from the output of the above command. Save the file. Then open up /etc/fuse.conf and add or uncomment the line:

user\_allow\_other

**Try mounting and unmounting using mount and unmount**

mount /home/ws\_username/www
ls /home/ws\_username/www
umount /home/ws\_username/www

**Setup auto-mount on connection (ifup) and auto-unmount on disconnect (ifdown)** Create a file /etc/network/if-up.d/mountsshfs with the following contents:

#!/bin/sh

## http://ubuntuforums.org/showthread.php?t=430312
## The script will attempt to mount any fstab entry with an option
## "...,comment=$SELECTED\_STRING,..."
## Use this to select specific sshfs mounts rather than all of them.
SELECTED\_STRING="sshfs"

# Not for loopback
\[ "$IFACE" != "lo" \] || exit 0

## define a number of useful functions

## returns true if input contains nothing but the digits 0-9, false otherwise
## so realy, more like isa\_positive\_integer 
isa\_number () {
    ! echo $1 | egrep -q '\[^0-9\]'
    return $?
}

## returns true if the given uid or username is that of the current user
am\_i () {
	\[ "$1" = "\`id -u\`" \] || \[ "$1" = "\`id -un\`" \]
}

## takes a username or uid and finds it in /etc/passwd
## echoes the name and returns true on success
## echoes nothing and returns false on failure 
user\_from\_uid () {
    if isa\_number "$1"
    then
		# look for the corresponding name in /etc/passwd
    	local IFS=":"
    	while read name x uid the\_rest
    	do
        	if \[ "$1" = "$uid" \]
			then 
				echo "$name"
				return 0
			fi
    	done </etc/passwd
    else
    	# look for the username in /etc/passwd
    	if grep -q "^${1}:" /etc/passwd
    	then
    		echo "$1"
    		return 0
    	fi
    fi
    # if nothing was found, return false
   	return 1
}

## Parses a string of comma-separated fstab options and finds out the 
## username/uid assigned within them. 
## echoes the found username/uid and returns true if found
## echoes "root" and returns false if none found
uid\_from\_fs\_opts () {
	local uid=\`echo $1 | egrep -o 'uid=\[^,\]+'\`
	if \[ -z "$uid" \]; then
		# no uid was specified, so default is root
		echo "root"
		return 1
	else
		# delete the "uid=" at the beginning
		uid\_length=\`expr length $uid - 3\`
		uid=\`expr substr $uid 5 $uid\_length\`
		echo $uid
		return 0
	fi
}

# unmount all shares first
sh "/etc/network/if-down.d/umountsshfs"

while read fs mp type opts dump pass extra
do
    # check validity of line
    if \[ -z "$pass" -o -n "$extra" -o "\`expr substr ${fs}x 1 1\`" = "#" \]; 
    then
        # line is invalid or a comment, so skip it
        continue
    
    # check if the line is a selected line
    elif echo $opts | grep -q "comment=$SELECTED\_STRING"; then
    	
    	# get the uid of the mount
        mp\_uid=\`uid\_from\_fs\_opts $opts\`
        
        if am\_i "$mp\_uid"; then
			# current user owns the mount, so mount it normally
			{ sh -c "mount $mp" && 
				echo "$mp mounted as current user (\`id -un\`)" || 
				echo "$mp failed to mount as current user (\`id -un\`)"; 
			} &
		elif am\_i root; then
			# running as root, so sudo mount as user
			if isa\_number "$mp\_uid"; then
				# sudo wants a "#" sign icon front of a numeric uid
				mp\_uid="#$mp\_uid"
			fi 
			{ sudo -u "$mp\_uid" sh -c "mount $mp" && 
				echo "$mp mounted as $mp\_uid" || 
				echo "$mp failed to mount as $mp\_uid"; 
			} &
		else
			# otherwise, don't try to mount another user's mount point
			echo "Not attempting to mount $mp as other user $mp\_uid"
		fi
    fi
    # if not an sshfs line, do nothing
done </etc/fstab

wait

Create another file /etc/network/if-down.d/umountsshfs with the following contents:

#!/bin/bash

# Not for loopback!
\[ "$IFACE" != "lo" \] || exit 0

# comment this for testing
exec 1>/dev/null # squelch output for non-interactive

# umount all sshfs mounts
mounted=\`grep 'fuse.sshfs\\|sshfs#' /etc/mtab | awk '{ print $2 }'\`
\[ -n "$mounted" \] && { for mount in $mounted; do umount -l $mount; done; }

Make both files executable and owned by root:

sudo chmod 755 /etc/network/if-up.d/mountsshfs /etc/network/if-down.d/umountsshfs
sudo chown root:root /etc/network/if-up.d/mountsshfs /etc/network/if-down.d/umountsshfs

**Test the working of scripts** Enter the commands (assuming the ethernet interface as eth0):

sudo ifdown eth0   #disconnect

sudo ifup eth0   #connect

Test if the directory is mounted:

ls /home/ws\_user/www #should list files

Disconnect:

sudo ifdown eth0

Test if the directory is unmounted:

ls /home/ws\_user/www #should not list files

Connect back:

sudo ifup eth0   #connect

You can also reboot the system to test if the directory properly mounts at startup.

**Start Apache and Test**

sudo service apache2 restart

Test using a web browser.

## References

[http://ubuntuforums.org/showthread.php?t=430312](http://ubuntuforums.org/showthread.php?t=430312) [https://bugs.launchpad.net/ubuntu/+source/sshfs-fuse/+bug/243298](https://bugs.launchpad.net/ubuntu/+source/sshfs-fuse/+bug/243298) [http://linux.dsplabs.com.au/sshfs-read-connection-reset-by-peer-p73/](http://linux.dsplabs.com.au/sshfs-read-connection-reset-by-peer-p73/) [http://www.debian-administration.org/articles/152](http://www.debian-administration.org/articles/152) [https://help.ubuntu.com/community/SSHFS](https://help.ubuntu.com/community/SSHFS)
