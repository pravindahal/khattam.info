---
title: "[HOWTO] Enable 'sudo' in Fedora 15"
date: "2011-05-31"
tags: 
  - "fedora"
  - "linux"
  - "nano"
  - "sudo"
  - "sudoers"
---

Here is how you can enable 'sudo' in Fedora so that you don't have to login as root everytime you need to run a command as root. Open up terminal and type in the following:

su #enter root password followed by this one
yum install nano
nano /etc/sudoers

Now, scroll down and you should see something like:

root    ALL=(ALL)	ALL

Just below that line, add this:

YOUR\_USER\_NAME\_HERE    ALL=(ALL)	ALL

For eg, my username is "khattam", so I added the line:

khattam    ALL=(ALL)	ALL

If you are not sure what your username is, open up a new terminal window and type in 'whoami'. Save by pressing Ctrl+O followed by Enter. Exit nano by pressing Ctrl+X. Exit from root by typing in "exit".

Now, you will be able to use sudo.
