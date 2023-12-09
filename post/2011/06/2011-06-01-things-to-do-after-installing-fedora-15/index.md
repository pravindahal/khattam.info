---
title: "20 Things to do after installing Fedora 15"
date: "2011-06-01"
tags: 
  - "7z"
  - "chrome"
  - "date"
  - "delete"
  - "deluge"
  - "desktop"
  - "evolution"
  - "fedora"
  - "firefox"
  - "flash-player"
  - "gimp"
  - "gnome-3"
  - "gnome-tweak-tool"
  - "google-chrome"
  - "google-video"
  - "google-voice"
  - "libreoffice"
  - "linux"
  - "media"
  - "nautilus"
  - "p7zip"
  - "parcellite"
  - "rar"
  - "shutdown"
  - "skype"
  - "sudo"
  - "terminal"
  - "thunderbird"
  - "torrent"
  - "unrar"
  - "vuze"
  - "yum-fastestmirror"
---

Here are few things you can do after installing Fedora 15 to make the experience better. You may have to [enable sudo](http://www.khattam.info/howto-enable-sudo-in-fedora-15-2011-05-31.html) to follow some of the tips or you can run the commands in terminal by logging in as root (su). The following are in no particular order. Feel free to skip the ones you do not need.

1\. [**Enable sudo**](http://www.khattam.info/howto-enable-sudo-in-fedora-15-2011-05-31.html)

2\. **Install yum-fastestmirror plugin** yum-fastestmirror selects the fastest mirror for updating and installing packages. It can be installed by running the following in the terminal:

sudo yum install yum-fastestmirror

3\. [**Add shutdown menu item permanently**](http://www.khattam.info/howto-add-shutdown-menu-item-permanently-on-gnome-3-2011-05-26.html)

4\. [**Install flash player**](http://www.khattam.info/howto-install-flash-player-in-fedora-15-2011-05-26.html)

5\. [**Add minimize, maximize title bar buttons**](http://www.khattam.info/howto-add-minimize-maximizerestore-buttons-in-gnome-3-2011-05-26.html)

6\. [**Enable delete key in Nautilus**](http://www.khattam.info/howto-enable-delete-key-in-nautilus-3-fedora-15-2011-06-01.html)

7\. [**Enable right click on desktop and add Desktop folder on the Desktop**](http://www.khattam.info/howto-enable-right-click-and-desktop-folder-in-gnome-3-2011-06-01.html)

8\. [**Show date on top panel**](http://www.khattam.info/howto-show-date-on-top-bar-in-gnome-3-2011-05-26.html)

9\. **Install nautilus open terminal** If you use terminal a lot, you may want to have "Open in terminal" in folders in Nautilus file manager. To do so, install the package nautilus-open-terminal

sudo yum install nautilus-open-terminal

10\. **Install a torrent client** If you download via torrents, you will need a torrent client. While Fedora ships with Transmission Torrent Cliene, I prefer Vuze (Azureus) (written in Java). It can be installed by running the following in the terminal:

sudo yum install azureus

You may also like deluge (written in Python, Gtk) which is also an excellent alternative. It can be installed by running the following in the terminal:

sudo yum install deluge

11. **Install Google Chrome** Although Firefox 4 is shipped by default, you may want to have a secondary browser or may prefer Google Chrome. You can simply download rpm from [Google Chrome download page](http://www.google.com/chrome/) and install it. The package will automatically insert repository information so that you get updates from update manager.

12\. **Install Libreoffice** Libreoffice is available in the repository. I recommend "Add/Remove Software" to select and install office tools you need. libreoffice-writer (Word processor) and libreoffice-calc (Spreadsheet) is all I need. You may also want libreoffice-impress (Presentation) and libreoffice-draw (Drawing).

13. **Install Thunderbird** I prefer Thunderbird to Evolution. You can install it from repository by running the following in the terminal:

sudo yum install thunderbird

14\. **Install a clipboard manager** If you do a lot of writing or programming, you will love a clipboard manager. I like parcellite and it is available in the repos as well. It can be installed by running the following in the terminal:

sudo yum install parcellite

UPDATE: You may also like another clipboard manager called [GPaste](http://www.khattam.info/howto-install-gpaste-in-fedora-15-2011-06-26.html "GPaste") which integrates well with Gnome Shell.

15\. **Install Google Voice and Video chat** If you use Google Voice, you can download and install rpm package from [Google Voice and Video Download page](http://www.google.com/chat/video/download.html).

16\. [**Add support for media formats**](http://www.khattam.info/howto-add-support-for-mp3-avi-and-other-media-formats-by-installing-codecs-in-fedora-15-2011-05-26.html)

17. **Install support for rar and 7z archive formats** Rar is a proprietary format but it is used widely and you may encounter rar files so it is handy to have it installed.

sudo yum localinstall --nogpgcheck http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-stable.noarch.rpm http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-stable.noarch.rpm
sudo yum install unrar

7z is also a popular format and it is also available in the repository.

sudo yum install p7zip p7zip-plugins

18. **Install Gimp** Fedora does not ship with an image editor. I prefer Gimp and it can be installed by running the following in the terminal:

sudo yum install gimp

19\. **Install gnome-tweak-tool to customize fonts, themes etc** gnome-tweak-tool can be installed by running the following in the terminal:

sudo yum install gnome-tweak-tool

Run it (press Alt+F2 and type in gnome-tweak-tool) and change the settings. It does not have OK or Apply and simply selecting the options performs the changes. Some changes may require logging out and logging back in.

20\. **Install skype** Skype is a popular text, voice and video chat tool. You can download and install rpm from [this link](http://www.skype.com/intl/en-us/get-skype/on-your-computer/linux/downloading.fedora). If you have 32-bit, installation will be straightforward. However, if you have 64-bit, please read [this post](http://www.khattam.info/howto-install-skype-in-fedora-15-64-bit-2011-06-01.html).

Please share what you did after installing Fedora 15 in the comments.
