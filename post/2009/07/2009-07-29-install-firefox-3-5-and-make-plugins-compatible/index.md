---
title: "[HOWTO]Install Firefox 3.5 in Jaunty Jackalope and Make Add-Ons Compatible"
date: "2009-07-29"
categories: 
  - "jaunty-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "add-on-compatibility"
  - "add-ons"
  - "default-for-html"
  - "firefox"
  - "firefox-3-5"
  - "jaunty"
  - "jaunty-jackalope"
  - "jaunty-ubuntu-repositories"
  - "linux"
  - "minefield"
  - "nightly-tester-tools"
  - "open-with"
  - "shiretoko"
  - "ubuntu"
  - "ubuntu-9-04"
---

Firefox 3.5 is out for other OSes however the final version is not available for Linux. This is how you install it on your Jaunty Jackalope installation. We will use the terminal for this. It is just a copy and paste from here to your terminal so it should be fine.

**Installation**  
**  
1\. Add the mozilla repository:** (Copy all the lines before step 2 at once, it is just a single line split because it was long. You may use triple click to select the whole line.)  
`sudo sh -c "echo 'deb http://ppa.launchpad.net/ubuntu-mozilla-daily/ppa/ubuntu jaunty main' >> /etc/apt/sources.list"`  
  
**2\. Add the launchpad key:**  
a. Get launchpad key updater  
`wget "http://files.getdropbox.com/u/1113424/launchpad-update.tar.gz"`  
b. Extract it  
`tar -xf launchpad-update.tar.gz`  
c. Install it  
`sudo mv launchpad-update /usr/bin`  
d. Add keys  
`sudo launchpad-update`

**3\. Update your package list:**  
`sudo apt-get update`

**4\. Install**  
`sudo apt-get install firefox-3.5`

Enter password when required and answer yes/no questions appropriately and it should be no problem.

**Launching the new browser**  
Now, after it is installed, you can launch it from Applications > Internet > Minefield 3.5 Web Browser and it will be called Shiretoko (I don't understand the brand names.. Minefield, Shiretoko.. for the same firefox-3.5? whatever). You may even launch it by doing a Alt+F2 and typing in firefox-3.5. And it should check for add-on compatibility and find updates to your add-ons. Choose to install the available updates.  
**  
Add-on Compatibility**  
But you will find some add-ons are not compatible and will therefore be disabled. To fix this, grab [Nightly Tester Tools add-on](https://addons.mozilla.org/en-US/firefox/addon/6543 "Nightly Tester Tools") and restart your browser. Now, goto Tools>Add-ons and then click on "Override all compatibility" on the lower right. This should fix the Add-ons so that they work with firefox-3.5.

Restart the browser and everything should be working.

**Firefox 3.5 as the default browser**  
Also, you'd like the default browser to be firefox-3.5 instead of firefox. To do that, goto System>Preferences and select Preferred Applications. Now, in Web Browser, select Custom and then replace firefox %s with firefox-3.5 %s. Now, your default browser is firefox-3.5.

You will also like your HTML files to open with the new firefox-3.5. Right click on any html file and then select Properties. In the Open with tab, select Minefield 3.5 Web Browser instead of Firefox Web Browser.

**More on Add-on Compatibility**  
We have seen how to make the old add-ons, that were already installed, compatible with the new browser by using Nightly Tester Tools. But what about the add-ons that were not already installed and that are not marked to be compatible with the new firefox-3.5 (like the add-on [here](https://addons.mozilla.org/en-US/firefox/search?q=cookieswap&cat=all "Cookieswap") called cookieswap.. as of now, it is marked as not compatible with firefox-3.5)?

We have a workaround and that will be to launch the older firefox 3.0 and then instead of clicking on the Add to Firefox button, right-click instead and Save>Link>As. Now in Firefox-3.5, goto Tools>Add-ons and then drag and drop the downloaded xpi file onto the Add-ons window.  
In case you have removed the older firefox and then you may use either User Agent Switcher to switch the User-Agent header to older version of Firefox or just use firebug to display the hidden download div. If this is difficult for you, go with the first workaround.

Hope this helps. Have a good day.

Please post any comments, suggestions, questions, corrections or feedback.
