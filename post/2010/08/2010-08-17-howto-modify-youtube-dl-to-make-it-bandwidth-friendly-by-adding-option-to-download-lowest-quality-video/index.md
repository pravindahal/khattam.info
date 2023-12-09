---
title: "[HOWTO] Modify youtube-dl to make it bandwidth friendly by adding option to download lowest quality video"
date: "2010-08-17"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "bandwidth-friendly"
  - "downloader"
  - "linux"
  - "lowest-quality"
  - "video-downloader"
  - "worst-quality"
  - "youtube"
  - "youtube-downloader"
  - "youtube-dl"
---

youtube-dl is a command line utility that can be used to download Youtube videos. It has many command line switches ; most notably -t to save the video with title of the video as filename, -c to continue the download instead of starting over. It can be installed in Ubuntu Lucid Lynx and Maverick Meerkat via Synaptic by enabling universe repository. Then running the following command will update it to the latest version:

sudo youtube-dl -U

If you want to use it in older Ubuntu releases or other Linux distros, visit the [official site](http://bitbucket.org/rg3/youtube-dl/). It also has a switch -f with which you can select a [Youtube Video Format](http://en.wikipedia.org/wiki/YouTube#Quality_and_codecs) to download. Like this:

youtube-dl -f 34 "http://www.youtube.com/watch?v=2\_VFKqw1q2Q"

That will download video with format code 34 if available. 34 is 360p flv format. You will need to know the formats to be able to use this options and all this information is available in [Youtube Wikipedia Article](http://en.wikipedia.org/wiki/YouTube#Quality_and_codecs). If the format you requested is not available, it will print the message:

> ERROR: unable to download video (format may not be available)

I don’t know why someone would like to do it, but an option f-1 is available which downloads all available qualities of the video. If you don’t provide any format information, it will download the best quality version of the video. You can always try your luck with the following formats that are supported for youtube, arranged in decreasing quality: 38, 37, 22, 45, 35, 34, 43, 18, 6, 5, 17, 13 That is, if format 38 is available, it will download it and if it isn’t it will download 37 and so on.

But what if you want to download the lowest quality or worst quality of video to be able to download quickly? It currently does not have such an option and we will add it. To do so, open it up in a text editor. I’m using gedit:

gksu gedit /usr/bin/youtube-dl

and then find the following code (in the version 2010.08.04 that I have, it starts in line 938):

			if requested\_format is None:
				video\_url\_list = \[(existing\_formats\[0\], get\_video\_template % existing\_formats\[0\])\] # Best quality
			elif requested\_format == '-1':
				video\_url\_list = \[(f, get\_video\_template % f) for f in existing\_formats\] # All formats
			else:
				video\_url\_list = \[(requested\_format, get\_video\_template % requested\_format)\] # Specific format

and now add an elif block as shown below:

			if requested\_format is None:
				video\_url\_list = \[(existing\_formats\[0\], get\_video\_template % existing\_formats\[0\])\] # Best quality
			elif requested\_format == '-1':
				video\_url\_list = \[(f, get\_video\_template % f) for f in existing\_formats\] # All formats
			elif requested\_format == '0':
				video\_url\_list = \[(existing\_formats\[len(existing\_formats)-1\], get\_video\_template % existing\_formats\[len(existing\_formats)-1\])\] # worst quality
			else:
				video\_url\_list = \[(requested\_format, get\_video\_template % requested\_format)\] # Specific format

Now, to download the worst quality version available, you can just pass -f 0 option i.e.

youtube-dl -f 0 "http://www.youtube.com/watch?v=2\_VFKqw1q2Q"

This should download the worst quality version and make the download size smaller. However, sometimes worst quality in the list does not mean smallest size (I had seen examples of this while I was doing a youtube downloader project a year ago, but don’t know any examples to point out right now), they should almost always be so.

If the developers want to implement this (the lowest size download feature) in the main project, I think the best way to do it is to actually query header information of the video url and find the actually sizes, compare them and then download the one with the least size.
