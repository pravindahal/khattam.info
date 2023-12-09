---
title: "[HOWTO] Command-line copy/paste files/directories in Linux"
date: "2010-10-27"
tags: 
  - "bashrc"
  - "bash"
  - "ccopy"
  - "command-line"
  - "copy"
  - "cpaste"
  - "linux"
  - "paste"
---

Command line copy and paste of files is handy for someone who likes working with the command line a lot. Here is how you can do with bash.

Open the file ~/.bashrc in gedit:

gedit ~/.bashrc

Add the following text at the end of the file:

ccopy () { 
touch /tmp/cclipboard; 
rm /tmp/cclipboard; 
dirlist=("$@")
for dir in "${dirlist\[@\]}"; do
        readlink -m "$dir" >>/tmp/cclipboard;
done;
}

cpaste(){ 
while read line
	do cp -R "$line" ./
done < /tmp/cclipboard 
}

Now, either restart the terminal or use the following command:

source ~./bashrc

To copy a file, use the following command:

ccopy /absolute/or/relative/path/to/file/or/directory

Top copy multiple itles, do this:

ccopy /absolute/or/relative/path/to/file/or/directory1 /absolute/or/relative/path/to/file/or/directory2

To paste the contents, navigate to the directory where you want to paste the contents and run the following command:

cpaste

Please feel free to report bugs and modify it to your liking.

Inspired from: [http://www.webupd8.org/2010/10/copy-paste-files-from-command-line-bash.html](http://www.webupd8.org/2010/10/copy-paste-files-from-command-line-bash.html)
