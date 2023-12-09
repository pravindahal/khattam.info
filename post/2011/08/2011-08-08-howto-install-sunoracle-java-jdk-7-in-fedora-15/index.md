---
title: "[HOWTO] Install Sun/Oracle Java JDK 7 in Fedora 15"
date: "2011-08-08"
tags: 
  - "fedora"
  - "firefox"
  - "java"
  - "jdk"
  - "jre"
  - "linux"
  - "oracle"
  - "sun"
---

Sun/Oracle Java JDK 7 may be required to run some applications that are not compatible with OpenJDK which can be installed using package manager in Fedora 15. Here is how to do it. Open the terminal and use the following commands:

**For 64-bit**

wget "http://download.oracle.com/otn-pub/java/jdk/7/jdk-7-linux-x64.rpm"
su -c 'rpm -i jdk-7-linux-x64.rpm'

**For 32-bit**

wget "http://download.oracle.com/otn-pub/java/jdk/7/jdk-7-linux-i586.rpm"
su -c 'rpm -i jdk-7-linux-i586.rpm'

If you already have OpenJDK/OpenJRE installed, you will need to configure your system so that the applications use the Sun/Oracle Java version instead of OpenJDK/OpenJRE. Here is how to do it:

su -c 'alternatives --install /usr/bin/java java /usr/java/jdk1.7.0/jre/bin/java 20000'
su -c 'alternatives --install /usr/bin/javaws javaws /usr/java/jdk1.7.0/jre/bin/javaws 20000'
su -c 'alternatives --install /usr/bin/javac javac /usr/java/jdk1.7.0/bin/javac 20000'
su -c 'alternatives --install /usr/bin/jar jar /usr/java/jdk1.7.0/bin/jar 20000'

**For 64-bit:**

su -c 'alternatives --install /usr/lib64/mozilla/plugins/libjavaplugin.so libjavaplugin.so.x86\_64 /usr/java/jdk1.7.0/jre/lib/amd64/libnpjp2.so 20000'

**For 32-bit:**

su -c 'alternatives --install /usr/lib/mozilla/plugins/libjavaplugin.so libjavaplugin.so /usr/java/jdk1.7.0/jre/lib/i386/libnpjp2.so 20000'

Hope this helps.
