---
title: "[SOLVED] java.security.AccessControlException: access denied (java.net.SocketPermission host connect,resolve)"
date: "2010-03-24"
categories: 
  - "lucid-ubuntu-linux-linux"
  - "ubuntu-linux"
tags: 
  - "java"
  - "java-net-socketpermission"
  - "java-security-accesscontrolexception"
  - "javascript"
  - "jdk"
  - "jre"
  - "linux"
  - "openjdk"
  - "sun-java"
  - "ubuntu"
  - "web"
  - "windows"
---

I am building a Java Applet which needs to connect to foreign host to operate. I created it and it runs good on OpenJDK Runtime Environment (IcedTea6 1.8pre) installed on my Ubuntu 10.04 Lucid Lynx Beta. But it does not run with Sun Java Runtime Environment 1.6.0\_18 on Windows. I don't know if it also does not work with Sun JRE in Linux. Also, as far as I know, OpenJDK/OpenJRE for Windows does not exist.

The applet shows somewhat this kind of when run in Windows under Sun JRE:

java.security.AccessControlException: access denied (java.net.SocketPermission host connect,resolve) 

and the page just stalls.

When I searched for help on the internet, I discovered that unsigned files do not run in Windows. So, I needed to sign it. The Certificate can cost at least a couple of hundred dollars for a month. If you are using it for commercial purposes, I advice you to buy a certificate. However, I just wanted my code to run in Windows and to do that I bundled the code inside a Jar file (I was just using the class file i.e. code="Classname.class". Now I need to use code="Classname" archive="JarName.jar" for applet in the HTML file.). So I am sharing what I did to make it run.

After building the Jar File (Netbeans IDE that I am using builds the Jar file automatically inside the dist sub-directory of the Project directory), I used the command

keytool -genkey

and entered the details. You can choose your own password for keystore. You can either use the same password for key password or choose a different one. Now a keyfile named .keystote is created in the home directory. I need to certify the key. Since I have not purchased a security certificate, I needed to certify it myself using the following command:

keytool -selfcert

. Now a key named mykey is created for me to use. This should only be done once.

Now, I changed my directory to the dist directory and executed the following command to sign a MyJarApplet.jar:

jarsigner -storepass KeySorePassword -keypass KeyPassPassword MyJarApplet.jar mykey

Here KeyStorePassword is the password used while creating the keystore and KeyPassPassword is the password used in the key mykey.

Now, the applet asks for authentication instead of showing nothing at all in Windows too.

Hope this helps.

References:  
[http://www-personal.umich.edu/~lsiden/tutorials/signed-applet/signed-applet.html](http://www-personal.umich.edu/~lsiden/tutorials/signed-applet/signed-applet.html)  
[http://java.sun.com/j2se/1.4.2/docs/tooldocs/solaris/jarsigner.html](http://java.sun.com/j2se/1.4.2/docs/tooldocs/solaris/jarsigner.html)  
[http://java.sun.com/j2se/1.4.2/docs/tooldocs/solaris/keytool.html](http://java.sun.com/j2se/1.4.2/docs/tooldocs/solaris/keytool.html)
