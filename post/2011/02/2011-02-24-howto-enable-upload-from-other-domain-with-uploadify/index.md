---
title: "[HOWTO] Enable cross-domain upload with uploadify jQuery plugin"
date: "2011-02-24"
tags: 
  - "ajax"
  - "crossdomain-xml"
  - "flash"
  - "jquery"
  - "upload"
  - "uploadify"
  - "web"
---

I have used uploadify v2.1.4 in one of my client's website. According to the requirements, a form in a website had to submit data to another website. The form also contained file uploads for which uploadify was being used. But uploadify does not support uploading from another site as it uses relative url. Also, flash does not support sending/receiving data to/from another site by default for security reasons.

The solution to the second problem is easy. All that needs to be done is placing a crossdomain.xml file in the root of the server where file is to be uploaded with allowed list of sites that can send/receive data from that site using flash. Here is an example of crossdomain.xml file which allows all the sites:

To solve the second server however, the core uploadify file must be edited. For version 2.1.4, the file is jquery.uploadify.v2.1.4.js. Search for "pathName" (without quotes) and find the following block of codes:

				var pagePath = location.pathname;
				pagePath = pagePath.split('/');
				pagePath.pop();
				pagePath = pagePath.join('/') + '/';
				var data = {};
				data.uploadifyID = settings.id;
				data.pagepath = pagePath;

Replace that with:

//				var pagePath = location.pathname;
//				pagePath = pagePath.split('/');
//				pagePath.pop();
//				pagePath = pagePath.join('/') + '/';
				var data = {};
				data.uploadifyID = settings.id;
				data.pagepath = "http://yourwebsite.here/path/to/folder/above/uploadify/folder";

In the above code, replace "http://yourwebsite.here/path/to/folder/above/uploadify/folder" with full URL of your site where you have uploadify folder. For instance, if you have an application in http://www.yoursite.com/myapp and uploadify directory inside myapp, i.e. http://www.yoursite.com/myapp/uploadify, you should enter pagepath value as: "http://www.yoursite.com/myapp". Also, make sure you include this edited javascript in the main page instead of the "min" version. Then, use the uploadify swf in uploadify directory in the new server.

Hope this helps.
