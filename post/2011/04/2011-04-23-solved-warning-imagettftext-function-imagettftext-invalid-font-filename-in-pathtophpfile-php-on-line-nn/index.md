---
title: "[SOLVED] Warning: imagettftext() [function.imagettftext]: Invalid font filename in path\to\php\file.php on line NN"
date: "2011-04-23"
tags: 
  - "font"
  - "gd"
  - "linux"
  - "php"
  - "wamp"
  - "web"
  - "windows"
  - "xampp"
---

I am running XAMPP 1.7.4 with PHP 5.3.5 on Windows 7. When using any text related GD library functions such as imagettftext(), I get the following error:

> \[SOLVED\] Warning: imagettftext() \[function.imagettftext\]: Invalid font filename in path/to/php/file.php on line NN

Normally, this happens when the font is missing in GDFONTPATH and can usually be resolved by using correct font folder, using correct font file and naming it properly in the PHP file. However, in this particular case, I've figured that this is the problem with GD Library or PHP because I am still getting the error even though I have done everything right. I tried WAMP but still in vain. When I tried the same in my Linux machine, everything was fine.

Here is what I did as a workaround. I removed the putenv line and referred to fonts by relative path. For example, the following sample code is the one that does not work

putenv('GDFONTPATH=' . realPath('fonts'));
$font="ariali";
imagettftext($image, $size, $angle, $xcordinate, $ycordinate, $text\_color, $font, $text);

I have assumed that the fonts folder contains a file ariali.ttf and in that case, the code must have worked. However, it does not, so the workaround is to do the following:

//putenv('GDFONTPATH=' . realPath('fonts')); remove this line
$font="fonts/ariali.ttf"; //use relative path here instead
imagettftext($image, $size, $angle, $xcordinate, $ycordinate, $text\_color, $font, $text);

The above code works and I guess this is how I will have to use fonts in PHP from now on.
