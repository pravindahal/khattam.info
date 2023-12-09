---
title: "[SOLVED] Module DateTime.DateTime, line 1145, in toZone"
date: "2010-08-19"
categories: 
  - "centos-rhel"
  - "lucid-ubuntu-linux-linux"
  - "maverick-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "datetime"
  - "linux"
  - "plone"
  - "python"
  - "tozone"
  - "web"
  - "zope"
---

I am using Ubuntu 10.10 Maverick Meerkat and live in Nepal, timezone Asia/Kathmandu. I have been trying to setup Plone CMS in my local computer for learning to build sites with Zope/Plone. However, I had been getting errors.

I installed Plone 3.3.5 on my Ubuntu 10.10 Maverick Meerkat 64bit Desktop with Plone Unified Installer - for Linux/BSD/OS X/UNIX/Solaris. The installation was successful.

Then I ran the instance of Zope by changing directory to where my Plone is installed and running the following in terminal:

cd /usr/local/Plone
sudo ./bin/instance fg

Then I could browse the url http://localhost:8080/manage (I had changed the port number to 8888 ).

However, when I tried to create a Plone Site using Zope interface, I got the following error:

> Site Error
> 
> An error was encountered while publishing this resource.
> 
> Error Type: KeyError Error Value: ''

I see the following error in the terminal:

> Module DateTime.DateTime, line 1145, in toZone KeyError: '' Unhandled exception in thread started by Traceback (most recent call last): File "/usr/local/Plone/Zope-2.10.11-final-py2.4/lib/python/ZServer/PubCore/ZServerPublisher.py", line 25, in \_\_init\_\_ response=b) File "/usr/local/Plone/Zope-2.10.11-final-py2.4/lib/python/ZPublisher/Publish.py", line 401, in publish\_module environ, debug, request, response) File "/usr/local/Plone/Zope-2.10.11-final-py2.4/lib/python/ZPublisher/Publish.py", line 227, in publish\_module\_standard if request is not None: request.close() File "/usr/local/Plone/Zope-2.10.11-final-py2.4/lib/python/ZPublisher/BaseRequest.py", line 211, in close notify(EndRequestEvent(None, self)) File "/usr/local/Plone/Zope-2.10.11-final-py2.4/lib/python/zope/event/\_\_init\_\_.py", line 23, in notify subscriber(event) File "/usr/local/Plone/Zope-2.10.11-final-py2.4/lib/python/zope/component/event.py", line 26, in dispatch for ignored in zope.component.subscribers(event, None): File "/usr/local/Plone/Zope-2.10.11-final-py2.4/lib/python/zope/component/\_api.py", line 130, in subscribers return sitemanager.subscribers(objects, interface) File "/usr/local/Plone/Zope-2.10.11-final-py2.4/lib/python/zope/component/registry.py", line 290, in subscribers return self.adapters.subscribers(objects, provided) AttributeError: adapters

I tried adding the following in buildout.cfg under instance section:

zope-conf-additional =
    
        TZ Asia/Katmandu
    

as instructed [here](http://bibekpaudel.wordpress.com/2009/11/26/solved-plone-installation-strange-error/) and running buildout again but this did not work for me as I got the same error again.

I then installed Ubuntu 10.04 Lucid Lynx 32bit Server in Virtualbox and installed Plone again. This time I used Python 2.4 from Hardy repository rather than having it built by Plone installer. I used the tutorial [here](http://plone.org/documentation/kb/installing-a-plone-buildout-on-ubuntu) for rest of the stuff. But I got the same error again.

I then thought it was a Ubuntu specific issue and then installed CentOS 5.5 minimal in Virtualbox and installed Plone again. This did not work either. The same error appeared.

I then installed Plone 4 using Python 2.6 but the same error appears in instance.log.

**Workaround** In the Virtualbox installation of Ubuntu 10.04, I changed the timezone to Asia/Alaska and then the problem was gone. To do so, I did the following:

sudo dpkg-reconfigure tzdata

And then I selected US, Alaska. I then changed the buildout.c I changed buildout.cfg to reflect the change in timezone:

zope-conf-additional =
    
        TZ US/Alaska
    

and ran buildout again.

sudo ./bin/buildout

Then the error no longer shows and I can create page.

I don't know if it is a python issue, or Datetime bug. I will dig into it later. But for now, Plone works.
