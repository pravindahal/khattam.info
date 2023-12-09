---
title: "[SOLVED] PHP Fatal error:  Call to undefined method Zend_Http_Client::setRawDataStream() in /path/Zend/Gdata/App.php on line X"
date: "2011-02-07"
tags: 
  - "http_client"
  - "php"
  - "setrawdatastream"
  - "web"
  - "zend"
---

I am trying to use Zend Gdata Library for uploading videos to YouTube. I was trying to test the [example provided](http://code.google.com/apis/youtube/2.0/developers_guide_php.html#Direct_Upload), but got into a problem running the example. Here was the error:

> PHP Fatal error: Call to undefined method Zend\_Http\_Client::setRawDataStream() in /usr/share/php/Zend/Gdata/App.php on line 661

It was because I had missed the part where I should have sent a Zend\_Gdata\_HttpClient() object while initializing Zend\_Gdata\_YouTube() object.

So, here is how I created Zend\_Gdata\_HttpClient() object and passed it to Zend\_Gdata\_YouTube() constructor. Also, video upload requires developer key which you can get from Google and username/password.

		require\_once('Zend/Loader.php'); // the Zend dir must be in your include\_path

		$authenticationURL= 'https://www.google.com/accounts/ClientLogin';
		Zend\_Loader::loadClass('Zend\_Gdata\_ClientLogin');
		$httpclient = Zend\_Gdata\_ClientLogin::getHttpClient(
			              $username = $user,
			              $password = $pass,
			              $service = 'youtube',
			              $client = null,
			              $source = 'An App Name', // a short string identifying your application
			              $loginToken = null,
			              $loginCaptcha = null,
			              $authenticationURL
			           );

		Zend\_Loader::loadClass('Zend\_Gdata\_YouTube');
		$yt = new Zend\_Gdata\_YouTube($httpclient,"An App Name","Version something or some desc","API-KEY");

Hope this helps.
