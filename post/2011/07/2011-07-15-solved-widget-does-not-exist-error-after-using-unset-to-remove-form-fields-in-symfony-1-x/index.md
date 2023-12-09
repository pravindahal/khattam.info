---
title: "[SOLVED] Widget does not exist error after using unset to remove form fields in Symfony 1.x"
date: "2011-07-15"
tags: 
  - "propel"
  - "symfony"
  - "web"
---

I am getting started with Symfony 1.4 and I learnt that form elements can be removed by using unset. However, I got error similar to the following after using unset:

> Widget 'x' does not exist

This was because the module still consisted of files referencing to those elements. So, it is necessary to re-generate module after making the changes. For example, if you are using Propel and if the module name is job and class name is JobeetJob in frontend, the following command should be run to re-generate module:

php symfony propel:generate-module --with-show frontend job JobeetJob

Hope this helps.
