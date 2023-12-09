---
title: "[HOWTO] Make Ubuntu 10.04 Lucid Lynx Mono Free"
date: "2010-08-14"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "net"
  - "ailurus"
  - "amarok"
  - "autopano-sift"
  - "avant-window-navigator"
  - "awn"
  - "banshee"
  - "bareftp"
  - "bashare"
  - "beagle"
  - "blam"
  - "bless-hex-editor"
  - "c"
  - "c-sharp"
  - "cairo-dock"
  - "cowbell"
  - "deskbar"
  - "devede"
  - "dfo"
  - "docky"
  - "dotgnu"
  - "dvdstyler"
  - "easytag"
  - "exaile"
  - "extcalc"
  - "f-spot"
  - "filezilla"
  - "flickr"
  - "freespeak"
  - "gbrainy"
  - "gftp-gtk"
  - "ghex"
  - "ghex2"
  - "gnome-do"
  - "gnome-rdp"
  - "gnome-subtitles"
  - "gnote"
  - "google-desktop"
  - "gq"
  - "graphmonkey"
  - "gthumb"
  - "gtkpod"
  - "gtwitter"
  - "gwibber"
  - "hardinfo"
  - "hipo"
  - "hugin"
  - "ipod"
  - "java"
  - "kflickr"
  - "kupfer"
  - "last-fm"
  - "lastfmproxy"
  - "lat"
  - "liferea"
  - "limewire"
  - "linux"
  - "luma"
  - "mandvd"
  - "mediainfo"
  - "microsoft-novell"
  - "mistelix"
  - "mono"
  - "mt-daap"
  - "muine"
  - "nitrogen"
  - "panorama"
  - "picard"
  - "pinot"
  - "python"
  - "remember-the-milk"
  - "reminna"
  - "rhythmbox"
  - "screenlets"
  - "shotwell"
  - "smuxi"
  - "streamdumper"
  - "subtitleeditor"
  - "sysinfo"
  - "tangerine"
  - "tasque"
  - "thelastripper"
  - "themonospot"
  - "tomboy"
  - "tovidgui"
  - "tracker"
  - "vala"
  - "wally"
  - "x-chat"
  - "xbmc"
  - "xchat"
  - "yarssr"
  - "youtranslate"
---

Ubuntu 10.04 comes with 3 default applications that depend on mono. They are F-Spot, a photo manager Tomboy, a note taking application Gbrainy, brain teaser game and trainer To get rid of mono and still keep the functionality, we need non-mono alternatives to these applications. Lets look at those. But first, let me write something about why someone may want to remove Mono.

**Why remove Mono?** There are several reasons why someone may want to remove Mono from their Ubuntu installation. You may want to gain some free space. Mono takes up a lot of space for just a few applications. If you remove and replace them with others. This may not seem important if you want to run Ubuntu off normal harddisks these days, but it may be crucial if you want to remaster Ubuntu with few added applications and still want to distribute it on a CD or limited sized USB drive. You may want to remove Mono for other reasons like it is an implementation of [standard set by Microsoft](http://en.wikipedia.org/wiki/Embrace,_extend_and_extinguish) or just because it is a short name for a [contagious disease](http://en.wikipedia.org/wiki/Epstein-Barr_virus).

**Why not remove Mono?** You may not want to remove Mono if you just want to free some space from your installation because it may not be the case when you start installing other applications based on Mono. You see, the alternatives also have dependencies and the different dependencies for all the alternatives may occupy more space than Mono. Also, Mono seems to be a popular platform and there are many great applications like Docky, Banshee, Beagle etc. which need it. Moreover, many new applications may come up which need Mono and you may have to install it anyway.

Enough of that. Now, lets get to the applications. **F-Spot** F-Spot is to be removed from default install from Ubuntu 10.10 Maverick Meerkat and is being replaced by Shotwell. So, you can install Shotwell as a replacement to F-Spot. There is yet another photo manager called Gthumb but I think Shotwell is the better choice.

**Tomboy** Tomboy is a really great note taking application. However, an almost exact clone which can import and use all the notes created by tomboy is available. It is called Gnote. Tomboy can be safely replaced with Gnote. Gnote is a C++ port of Tomboy and claims to be faster. Also, if you use the [gnote stable ppa](https://launchpad.net/~gnote/+archive/ppa) by adding ppa:gnote/ppa to your software sources, you can install gnote 0.7.x which features a nice gnome-panel applet for Gnote.

**Gbrainy** I don't know a good replacement for this great game, but it is just a mind teaser game. So, if you can do without it, just remove it.

Following is the step by step procedure for doing this.

**Repositories** Open up Synaptic (System>Administration>Synaptic Package Manager) and click on Settings>Repositories. Make sure "Community maintained open source software (universe)" is selected. Now click Other Software tab and click Add. Then copy/paste the following

ppa:gnote/ppa

and click Add Source. This will add gnote PPA so that you can install the latest version of Gnote. Close the repositories window. Click on Reload so that the software lists are fetched from all repositories.

**Removal of Mono and Installation of Alternatives** Search for shotwell and gnote in Synaptic Package Manager and mark them for installation. Search for mono-runtime and mark it for removal. This will ask for your confirmation that several other mono related packages including F-Spot, Tomboy and Gbrainy will be marked for removal. Just confirm it and click on Apply. This should free about 40 MB of Disk Space and download about 3 MB only. To add Gnote panel applet, press Alt+F2 and type in killall gnome-panel and then when the panel loads back, Right click on it and select Add oo Panel, search for Gnote and click Add.

**Other Softwares that depend on mono and alternatives** There are few other great softwares based on mono that are great but aren't included in the default install. However, lets discuss them too. If you have any of those installed, they will be removed too. So, lets get to their alternatives.

**Docky** Many Ubuntu users use Mac OS like docks these days. One such great dock is Docky. But there are some other good docks which can serve as a replacement for Docky. One of them is Avant-Window-Navigator. It is not so friendly in terms of disk space though. It consumes over 40MB of disk space and hence defeats the purpose if you are trying to remove mono because of disk space usage. Cairo dock may serve as a good replacement in that case.

**Banshee** Banshee is a popular music player and media management application and favorite gnome media manager for lot of Linux users. However, the default Music Manager Rhythmbox should serve as a good replacement for it for a lot of users. Exaile is also good one.

**Gnome-do** I never really got used to this application. I primarily used it for Docky (Docky was originally a part of Gnome-do) and never used other features that it had to offer. However, there are some huge fans of this application. It claims to get things done faster in Gnome. There is another application called kupfer (it is not a KDE application as the name suggests, yes I'm talking about its initial letter :D) which claims to to provide similar functionality. It also has a lot of plugins and you should really give it a try. But it does not look sleek as Gnome-do though.

**Beagle** Beagle is a indexing and searching tool for the Desktop. Tracker, Pinot or Google-Desktop-Search should serve as replacements.

**Bless Hex Editor** Bless is a GUI hex editor which is really awesome. There is a replacement called ghex for it but it is not as good though.

**Muine Music Player** Muine is a simple music player. It aims to be and remain simple music player. I haven't really used it but I think the default movie player Totem, which can be used as audio player too of course, can provide everything that Muine has to offer.

**Graphmonkey** This one is a graph drawing application written in GTK#. I found a replacement called extcalc (qt3 application) but it is not as simple (which in other words also means it is more powerful and includes more features such as scripting :)).

**Tangerine** Tangerine is a DAAP server which can serve music to Apple iTunes, Rhythmbox, Banshee, Amarok, XBMC, Limewire or any other music player that supports this protocol. I haven't actually used it but there is another package mt-daapd which claims to provide similar functionality.

**Smuxi** It is an IRC client. There are several IRC clients that should replace it. I use X-Chat.

**Mistelix** Mistelix is a DVD authoring application. I don't actually do any of that, but according to this article, one or a combination of Q DVD-Author, DVDStyler, DeVeDe, ManDVD, and tovidgui should be able to provide what Mistelix does.

**gtwitter** This is a twitter client. The default application Gwibber should be a good replacement for this.

**gnome-rdp** gnome-rdp is a remote desktop client for Gnome. It can be replaced by reminna.

**Cowbell** It claims to be a music organizer and tagger. I am assuming EasyTag or Picard should serve as a replacement.

**Tasque** Tasque brings [Remember The Milk](http://www.rememberthemilk.com/) service (TODO list management) to the Desktop. However, Avant Window Navigator, Screenlets or Deskbar can offer similar functionality with RTM-related plugins.

**Blam** Blam is an RSS Aggregator. Liferea, Yarssr and many other applications provide this functionality.

**DFO** DFO (Desktop Flickr Organizer) is a photo manager which integrates with Flickr. I think only Kflickr (KDE Based) comes as close.

**Drapes** Wallpaper rotator for Gnome. Nitrogen and Wally should serve as replacements.

**gshare/giver** These are easy file sharing applications. BaShare can serve as a replacement.

**last-exit** It is a Desktop Last.fm player. Rhythmbox or lastfm should serve as a replacement.

**LAT** LAT is a LDAP Administration tool. Luma or GQ can serve as replacements.

**themonospot** It is a simple media information extractor. [MediaInfo](http://mediainfo.sourceforge.net/) serves as an excellent replacement.

**bareftp** Bareftp is a FTP client. Filezilla Client, gFTP-GTK and various other GUI FTP clients can replace bareftp.

**hipo** It is an iPod manager. gtkpod serves as a replacement.

**Sysinfo** It is a System Information Tool. It can be replaced with Hardinfo. [Ailurus](http://code.google.com/p/ailurus/downloads/list) also has this feature.

**thelastripper** It is a Last.fm stream dumper. lastfmproxy and streamdumper can be used to do the same.

**gnome-subtitles** Gnome subtitles is a sub-title editor. SubtitleEditor can serve as a replacement.

**autopano-sift** Panorama images creation helper. Hugin should be a replacement.

**youtranslate** It is a translation application which makes the use of online translators such as Google Translate. freespeak should serve as a good replacement.

**Mono** Mono is an open source, cross-platform, implementation of C# and the CLR that is binary compatible with Microsoft .NET. If you don't want to use it but still want to develop C# applications that run on Linux, you can go for dotGNU. But unlike Mono, it is not available from Ubuntu software center or officially supported by Cannonical.

**C#** If you want to develop cross platform applications or applications for Linux and don't want to use Mono, C# is not the language you should go with. A better language may be Java, Python or Vala.

**Final Notes** I have tried to list all the applications that may prevent you from removing mono. However, I have not used all the programs that I have listed (at least not used them enough to get used to them or to know what features they offer or even to the extent to know them in any way). So, if you think I have missed a program or an alternative, please let me know via comments. Thank you for reading.
