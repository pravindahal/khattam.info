---
title: "[HOWTO] [UPDATED] Add Widgets to Notepad-Chaos Wordpress Theme"
date: "2009-05-17"
tags: 
  - "notepad-chaos"
  - "web"
  - "widgets"
  - "wordpress"
---

UPDATE: As wordpress does not show characters correctly, the codes below may not work. So please do copy the codes from [this](http://www.khattam.info/notepad_chaos_read_instructions.tar.gz) file I have uploaded. Please read the post as well as the instructions included in the file. You may need to use WinRAR or 7zip to extract the file if you are running Windows.

The theme I'm using in this blog is widget unaware Notepad-Chaos theme. However, I have managed to allow it to add widgets.

I created a new file named functions.php in the directory wp-content/themes/notepad-chaos and put in the following code: <?php if ( function\_exists('register\_sidebar') ) register\_sidebar(array('name'=>'sidebar1', 'before\_widget' => '', 'after\_widget' => '', 'before\_title' => '<h4>', 'after\_title' => '</h4>', )); register\_sidebar(array('name'=>'sidebar2', 'before\_widget' => '', 'after\_widget' => '', 'before\_title' => '<h4>', 'after\_title' => '</h4>', )); register\_sidebar(array('name'=>'sidebar3', 'before\_widget' => '', 'after\_widget' => '', 'before\_title' => '<h4>', 'after\_title' => '</h4>', )); register\_sidebar(array('name'=>'sidebar4', 'before\_widget' => '', 'after\_widget' => '', 'before\_title' => '<h4>', 'after\_title' => '</h4>', )); register\_sidebar(array('name'=>'sidebar5', 'before\_widget' => '', 'after\_widget' => '', 'before\_title' => '<h4>', 'after\_title' => '</h4>', )); register\_sidebar(array('name'=>'sidebar6', 'before\_widget' => '', 'after\_widget' => '', 'before\_title' => '<h4>', 'after\_title' => '</h4>', )); ?>

So as to support a maximum of 6 widgets. Then, I opened up sidebar.php in the same directory and added in the following code at the end:

<?php if ( !function\_exists('dynamic\_sidebar') || !dynamic\_sidebar('sidebar1') ) : ?> <?php endif; ?>

<?php if ( !function\_exists('dynamic\_sidebar') || !dynamic\_sidebar('sidebar2') ) : ?> <?php endif; ?>

<?php if ( !function\_exists('dynamic\_sidebar') || !dynamic\_sidebar('sidebar3') ) : ?> <?php endif; ?>

<?php if ( !function\_exists('dynamic\_sidebar') || !dynamic\_sidebar('sidebar4') ) : ?> <?php endif; ?>

<?php if ( !function\_exists('dynamic\_sidebar') || !dynamic\_sidebar('sidebar5') ) : ?> <?php endif; ?>

<?php if ( !function\_exists('dynamic\_sidebar') || !dynamic\_sidebar('sidebar6') ) : ?> <?php endif; ?>

so as to support a maximum of 6 widgets to the sidebar. You may choose to edit the template elsewhere to place the widget as you like. Remember the names though (sidebar1, sidebar2, sidebar3 etc.) as you will need to know where the widget you are adding will go.

Now go to http://yoursite/wp-admin/widgets.php and you should be able to add widgets you choose.

Have Fun!

References: [How to Widget-Enable Wordpress Themes in 3 Easy Steps](http://www.quickonlinetips.com/archives/2007/11/how-to-widget-enable-wordpress-themes-in-3-easy-steps/ "Widger-Enable Wordpress Themes") [Multiple Dynamic Sidebars in Wordpress](http://www.quickonlinetips.com/archives/2007/11/how-to-create-multiple-dynamic-sidebars-for-wordpress-widgets/ "Multiple Dynamic Sidebars")

[![DreamTemplate - Web Templates](http://www.tqlkg.com/hj115y7B-53PTWRTQVZPRQUVZZXT)](http://www.jdoqocy.com/od98iqzwqyDHKFHEJNDFEIJNNLH)
