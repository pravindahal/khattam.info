---
title: "[HOWTO] Show space, tabs and newlines (invisibles) in Atom 1.x"
date: "2015-12-07"
categories: 
  - "mac"
tags: 
  - "atom"
  - "atom-1-x"
---

The default setting in Atom 1.x seems to be to not show the invisible characters. I tried to search how to enable this but I only found answers for old version . I had to go to the [documentation page](https://atom.io/docs/latest/using-atom-basic-customization) which was not easy to find so I am posting the solution here.

To enable showing invisible characters, all you have to do is open config.cson file (Atom->Open Your Config on Mac OS X) and add showInvisibles: true under editor so that the config file looks like the following:

  editor:
    invisibles: {}
    showInvisibles: true

Hope this helps!
