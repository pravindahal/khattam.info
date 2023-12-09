---
title: "[SOLVED] \"[[WARNING]] The posix_isatty() is available: FAILED *** Install and enable the php_posix extension (used to colorized the CLI output) ***\""
date: "2011-07-14"
tags: 
  - "apc"
  - "fedora"
  - "linux"
  - "php-posix"
  - "php-process"
  - "php_posix"
  - "posix_isatty"
  - "sympfony"
  - "web"
---

I ran the Symfony PHP Framework configuration check script in Fedora 15 and got the following error:

> \[\[WARNING\]\] The posix\_isatty() is available: FAILED \*\*\* Install and enable the php\_posix extension (used to colorized the CLI output) \*\*\*

To enable this extension, you should install php-process from Add/Remove Software or using yum.

su -c 'yum install php-process'

Run the check\_configuration.php again and you should not see this warning again.

**UPDATE:** If you also see the following:

> \[\[WARNING\]\] A PHP accelerator is installed: FAILED \*\*\* Install a PHP accelerator like APC (highly recommended) \*\*\*

and want to have a PHP accelerator, you can install php-pecl-apc:

su -c 'yum install php-pecl-apc'
