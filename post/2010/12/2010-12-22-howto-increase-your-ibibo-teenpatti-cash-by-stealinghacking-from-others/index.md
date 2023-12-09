---
title: "[HOWTO] Increase your ibibo TeenPatti Cash by stealing/hacking from others"
date: "2010-12-22"
tags: 
  - "cheat"
  - "hack"
  - "ibibo"
  - "steal"
  - "teen-patti"
  - "teenpatti"
  - "teenpatti-hack"
  - "web"
---

Ibibo Teen patti is a widely played online card game. It is flash game available as Facebook application. It can also be played directly from ibibo.com.

Me and my friends have found a vulnerability which allows stealing from any player online. In this post, I will describe how to steal ibibo cash from Facebook users only. Stealing from ibibo.com players is also basically same, however in this post I will focus on stealing from Facebook users only. Read along for how to.

_**Disclaimer:** Using the information in this page to steal ibibo cash from others may not be compliant with ibibo's terms of service. This article is for educational purposes only. The author will not be responsible for anything you do with the information in this page._ _**Note:** This hack works perfectly at the time of writing this. However, it may be fixed in the later version of ibibo Teen Patti._

## Tools

[Firefox](http://www.mozilla.com/en-US/firefox/) with [Firebug addon](http://getfirebug.com/). Note to Firefox 4 users: As of now, stable version of Firebug is not compatible with Firefox 4. Please see [Howto install Firebug in Firefox 4](http://www.khattam.info/howto-install-firebug-in-firefox-4-2010-12-03.html).

## Other Requirements

You need at least 3 players to play. You can login as 3 users yourself in the same computer (using multiple browsers or multiple browser profiles) or you can use help from 1 or two friends, but do note that you need a total of 3 accounts logged into Facebook at the same time. You also need a link to Facebook profile page (only the profile page URL, eg: http://www.facebook.com/user.name, not the login credentials) of a user who has a lot of ibibo cash. It can be your friends or anyone who has a lot of cash. Lets call the three users A, B and U (you) and the victim (whose cash you want to steal) as V for simplicity. It is also better to have the friends online (preferably voice chatting) or in the same room so that you can discuss your moves.

## Precautions

This will not work properly if V is playing ibibo at the same time. Try to make sure that V is not online (if possible). Otherwise the process will most likely be interrupted. Also, note that in this tutorial, U will be making your friends A and B rich with V's money. Later you can switch roles and ask them to follow this tutorial to make U rich.

## Setup

Login to Facebook and connect to ibibo Teen Patti application. Make sure A, B and U are in the same server. Choose a room with the least number of people with lots of empty tables and join the same room. Don't join any tables yet.

## Getting access to V's money

The idea here is that U get access to V's money, play with your friends B and C and make them win. **Step 1:** To do that, you will need to open V's Facebook Profile Page. In the profile page, Click on View>Page Source (or press Ctrl+U) and search for "user:" (without quotes) and you will find something like this:

Env={user:9999999999,locale:

Copy the number next to "user:" (9999999999 in the above example) and close the profile page. **Step 2:** Go to the page where you have opened Teen Patti Facebook Application and click on the Firebug icon (in the status bar of Firefox), and then the Firebug window will come up. Click on the arrow on top (inspect) and then click on the playing area of ibibo teenpatti. In the Firebug window, you should be able to see username= field. Edit it to replace it with V's profile ID (eg. 9999999999) you copied earlier. Then, find ../TeenPatti/TeenPattiLoaderX-Y.swf in the same embed code. Add a questionmark at the end of the swf followed by anything you like (so that it looks like ../TeenPatti/TeenPattiLoader1-0.swf?anything\_you\_like or just ../TeenPatti/TeenPattiLoader1-0.swf?) and press enter.

If you are confused, watch [this video](https://mega.nz/file/5hAkFTob#aUIdqB4opemyL95JRB4K1QAo5ijQCLmbcMkrKzNb6YE) to see this step in action.

Once you have done this, the game will reload. After reload, you will be logged in to the application as the victim V and have access to V's money.

## Play and Lose

Now, join an empty room and start a game. Increase the bid as much as you can and always pack or go "Back to Lobby". Give away as much money as A and B want.

## Additional Tips

\# Communicate all along the process so that everything goes good. # Join new empty room each time so that you can skip the 15 seconds wait. # Ask your friends to play blind and double each time they play, and U double too, so that V loses more than s/he normally would. # If your friends A for example, runs out of money, U and B simply click "Back to Lobby" and A will still win. # Watch out for intruders. If there is someone else in the room already, don't join.

When A and B are done, Suggest A or B to follow the same thing as U did so that you can win next time.

Best of Luck.

## Special Thanks To

fr3ak, \[A\]bu
