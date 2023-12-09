---
title: "A simple animated text stereogram in Javascript"
date: "2010-11-16"
tags: 
  - "animated"
  - "stereogram"
  - "text-stereogram"
  - "web"
---

<?php echo " #box1{ font-family: monospace; float: left; } #box2{ font-family: monospace; margin-left: 135px; } #fly1{ margin-left: 35px; } #fly2{ margin-left: 30px; } "; ?>

This is an animated stereogram by me \_khAttAm\_ created as a hobby

This is an animated stereogram by me \_khAttAm\_ created as a hobby

Make sure you can view stereograms or practice well or it will not make sense. // <!\[CDATA\[ var i=35; var dir="right"; var fly1=document.getElementById("fly1"); function varyI(){ fly1.style.marginLeft=i+"px"; if(dir=="right"){ if(i0){ i--; } else{ dir="right"; } } cb(); } function cb(){ setTimeout(varyI, 80); } varyI(); // \]\]>
