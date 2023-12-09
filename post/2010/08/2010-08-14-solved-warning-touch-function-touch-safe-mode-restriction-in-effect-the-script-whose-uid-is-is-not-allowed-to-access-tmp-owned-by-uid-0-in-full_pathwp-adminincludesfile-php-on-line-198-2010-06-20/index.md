---
title: "[SOLVED] Warning: touch() [function.touch]: SAFE MODE Restriction in effect. The script whose uid is  is not allowed to access /tmp owned by uid 0 in /full_path/wp-admin/includes/file.php on line 198"
date: "2010-08-14"
tags: 
  - "dedicated-server"
  - "linux"
  - "safe-mode-restriction"
  - "shell-access"
  - "ssh"
  - "web"
  - "wordpress"
---

I have moved one of my blogs to new server and I also updated to WordPress 3.0 at the same time. When I tried to update or add plugins, I got this error:

Warning: touch() \[function.touch\]: SAFE MODE Restriction in effect. The script whose uid is  is not allowed to access /tmp owned by uid 0 in /full\_path\_to\_wordpress/wp-admin/includes/file.php on line 198 
Download failed. Could not create temporary file.

I have PHP Safe mode enabled in my server and don’t wish to disable it. So, I decided to give out a new temporary folder for wordpress installation. I created a folder named tmp in my wordpress installation directory and made the user of the temporary directory same as the user of /full\_path\_to\_wordpress/wp-admin/includes/file.php. The following command shows the user, group and other details of a file:

ls -la /path/to/file

and the following can be used to make the directory writable and change the owner of the tmp directory to the same user displayed by the above command:

chmod 777 /path/to/file\_or\_dir
chown username /path/to/file\_or\_dir

Now, the following code must be appended to wp-config.php:

define('WP\_TEMP\_DIR','/full/path/to/tmp');

That did it for me. You will need shell access to your server to do this. If you do not have shell access, you should ask your hosting provider for help.
