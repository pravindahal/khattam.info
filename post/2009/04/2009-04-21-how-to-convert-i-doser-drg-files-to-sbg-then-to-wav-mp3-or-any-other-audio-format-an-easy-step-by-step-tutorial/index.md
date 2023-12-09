---
title: "How to Convert I-Doser DRG Files to SBG &amp; then to WAV, MP3 - An easy step by step tutorial"
date: "2009-04-21"
tags: 
  - "drg-to-mp3"
  - "drg-to-sbg"
  - "drg-to-wav"
  - "idoser"
  - "i-doser"
  - "i-doser-drug-files"
  - "idoser-drub-files"
  - "windows"
---

**What is I-Doser??**  
The I-Doser application scientifically synchs your brainwaves to achieve a specific mood or experience, as outlined by the dose you are taking. It does this through the use of a binaural beat dose that changes your brainwave patterns to make you feel a certain way. Binaural brainwave doses for every imaginable mood.

**What are drg files??**  
.drg files are I-Doser drug files available in I-Doser store, which can be played in I-Doser application once. After playing it once, you will not be able to play it anymore. You will have to buy the dose again to play the dose again. According to I-Doser disclaimer "Doses are one-time use files for use through the I-Doser Application."  
EDIT: As of Version 4.x, you can play doses multiple times.

For further information about I-Doser and doses, visit http://www.I-doser.com.

**Disclaimer:**  
We were going to talk about how to convert these doses to Wav. This may be illegal. But I haven't found anything said in I-Doser that says doing so is illegal. However, use this tutorial at your own risk. Me or any of the owners of media hosting this tutorial will not be responsible for what you do with information from this tutorial. Please be warned.

**What this tutorial is not about??**  
Please be informed that this tutorial is NOT about playing a dose and recording it with third party recording software. Recording with third party application such as JetAudio, Total Recorder etc. is also an option, but you may experience loss of sound quality and thus complete effects of doses may not be experienced.

**Background Information:**  
I-Doser is a rip off of an Open Source program called Sbagen. Sbagen is a Brain-Wave generating program, which comes with some presets for enhancing and relaxing your brain. This application has a preset file (.sbg) which can be played and recorded to wav too. So, if we have Sbagen and the sbg of the drug, we will easily be able to record it with the help of Sbagen and this should record sbg files with no loss of quality.

And what are the drg files that come with I-Doser?? A .drg file is just an encrypted .sbg + information about the dose and the screenshot.

So, you may be thinking that we will need to de-crypt this file and obtain the sbg. But it is much more simpler than you thought. Read on...

**Duplicating Doses:**  
EDIT: ignore this section if you are using I-Doser version 4 or newer.  
For trying this tutorial, you may need to open the dose file again and again in I-Doser, which is not permitted by I-Doser software. You can bypass this with any of the following methods:

Method 1:  
1\. Get a cracked version of I-Doser.  
2\. Play doses as many times as you like.

Method 2:  
1\. Open regedit and navigate to HKEY\_CURRENT\_USER\\Software\\VB and VBA Program Settings\\IDoser\\  
2\. Delete the key drgMBUN so that all the values in the key get deleted. Then you will be able to play any played dose again.  
3\. Play and enjoy. However, to replay it again, you will need to follow steps 1 and 2 again.

Method 3:  
1\. Open the already played .drg file in a text editor. Notepad will do.  
2\. Change the first line of the file from Q??????? to anything.  
3\. Play the dose and enjoy. To replay the dose, you will need to change the first line to something else again.

**Tools Required for convertion to wav:**  
We need only two tools and they are:

1\. **I-Doser** itself. Get it from I-Doser.com if you haven't already downloaded it. Version 3 is available in the time this tutorial is written. However, you may also use version 4 beta.(not available to public now).  
EDIT: The current version is version 4.5 and this tutorial works flawlessly with it.  
UPDATE: Not required if using [Online DRG to SBG Converter.](../drg2sbg/ "DRG to SBG Converter")

2\. **Sbagen**. Get it from [http://uazu.net/sbagen/](http://uazu.net/sbagen/ "Sbagen") or just Google for it. Download the Windows installer version.

Download and install both applications before you continue.

**Procedure:**

**Part I: Obtaining the sbg file from the drg:**  
**(Method I - I-Doser temp.xqp Method)  
**1\. Launch I-Doser and Open the dose file. (For I-doser version 3 and earlier: If you have already opened the .drg file once, read Duplicating Doses section above.)  
2\. Hit "Play dose" and leave it.  
3\. Now, navigate to the folder you have installed I-Doser to. This should be your Program Files\\I-Doser directory or wherever you have installed it.  
EDIT: Vista users who have installed I-doser without administrator privilages may need to navigate to \\Users\\%username%\\AppData\\Local\\VirtualStore\\Program Files\\IDoser v4 to find the installation directory.  
4\. Look for a file named temp.xqp.  
5\. Copy this file to another location such as your desktop.  
6\. Open temp.xqp with notepad and you will see it is readable to some extent, as compared to the .drg files.  
7\. Now, add "-SE" without quotes in the first line of the temp.xqp file so that it looks like:

\-SE

alpha10: pink/40 300+10/60  
alpha12: pink/40 300+12.25/60  
............................  
............................

8\. Save the file as "something.sbg" WITH quotes so that it is saved with an sbg extention.

**(Method II - Online DRG to SBG Converter Method)**  
1\. Open up [Online DRG to SBG Converter](http://www.khattam.info/drg2sbg/ "Online DRG to SBG Converter").  
2\. Click on Browse and select the DRG file you want to convert.  
3\. Press the Press to Upload button.  
4\. Save the file.

**Part II: Converting to Wav.**  
1\. Now, right click the newly saved file. If you have Sbagen installed, you will see a "Write to Wave" option. Click it and wait for a few minutes till recording is done.  
2\. You will see a Out.wav file in the same directory where the .sbg file is located. Rename it to something else, if you want to convert another file, else your out.wav will be overwritten.  
3\. Play the wav file dose in your favourite media player or burn it to a DVD\\CD or your MP3 player\\PMP and enjoy.

Note that if you convert it to some other formats (such as MP3), the doses may not be effective. However, you can convert to MP3 by using converters such as Audacity+lame.

Also note that Right and Left speakers of your headphones should be placed in correct ears for the doses to function and you should have high quality stereo headphones. And speakers do not work. You will need headphones for I-Doser to work.

PS: Hope this tutorial is easy to follow and is understandable. My native language is not English so pardon me for mistakes.

PPS: This artically was originally posted by me at [ThinkDigit Forums](http://www.thinkdigit.com/forum/showthread.php?t=54643 "How to convert I-Doser .DRG Files to WAV") and then later moved to [The I-Doser Blog](http://theidoserblog.blogspot.com/2008/01/how-to-convert-i-doser-drg-files-to-wav.html "how to convert i-doser drg files to wav"). Please goto the above links to view older comments to the tutorial.
