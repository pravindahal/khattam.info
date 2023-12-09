---
title: "[SOLVED] IOError: Profile archgenxml_profile.xmi not found"
date: "2010-09-24"
tags: 
  - "archgenxml"
  - "linux"
  - "plone"
  - "web"
---

I am following through the book "Plone 3.3 Products Development Cookbook" and encountered an error while using archgenxml as specified in Page 58:

cd ~/libexec/archgenxml/models
../bin/archgenxml ./poxContentTypes.zargo

The error is as follows:

> INFO ArchGenXML Version 2.4.1 (c) 2003-2009 BlueDynamics Alliance, Austria, GPL 2.0 or later INFO Parsing... Traceback (most recent call last): File "../bin/archgenxml", line 19, in ? archgenxml.ArchGenXML.main() File "/home/pravin/libexec/archgenxml/eggs/archgenxml-2.4.1-py2.4.egg/archgenxml/ArchGenXML.py", line 114, in main gen.parseAndGenerate() File "/home/pravin/libexec/archgenxml/eggs/archgenxml-2.4.1-py2.4.egg/archgenxml/ArchetypesGenerator.py", line 4127, in parseAndGenerate profile\_dir=self.options.option('profile\_dir')) File "/home/pravin/libexec/archgenxml/eggs/xmiparser-1.4-py2.4.egg/xmiparser/xmiparser.py", line 2813, in parse raise IOError("Profile %s not found" % fn) IOError: Profile archgenxml\_profile.xmi not found

I ran the help for archgenxml by executing the following:

../bin/archgenxml --help

I noticed the option --profile-dir with which I could specify the directory containing profiles. It was expected to look into profiles directory, but it did not. So, the following command generates the contents as required:

cd ~/libexec/archgenxml/models
../bin/archgenxml ./poxContentTypes.zargo --profile-dir=../profiles/

This did the job.
