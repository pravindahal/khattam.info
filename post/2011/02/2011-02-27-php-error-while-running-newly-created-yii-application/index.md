---
title: "PHP Error while running newly created Yii Application"
date: "2011-02-27"
tags: 
  - "php"
  - "php-5-3"
  - "web"
  - "yii"
---

If you are using PHP 5.3 and have created a new Yii! Framework 1.1 application, you will get the following error:

date(): It is not safe to rely on the system's timezone settings. You are \*required\* to use the date.timezone setting or the date\_default\_timezone\_set() function. In case you used any of those methods and you are still getting this warning, you most likely misspelled the timezone identifier. We selected 'Your/Timezone' for 'Timezone Info' instead 

To get around this, just open up index.php of your application and in the first line, add the following:

date\_default\_timezone\_set('Timezone/String');

You should replace the 'Timezone/String' with your timezone information. Since my timezone is Asia/Kathmandu, I used:

date\_default\_timezone\_set('Asia/Kathmandu');

Hope this helps.
