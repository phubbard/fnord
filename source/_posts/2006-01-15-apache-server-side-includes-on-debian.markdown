---
date: '2006-01-15 16:26:52'
layout: post
slug: apache-server-side-includes-on-debian
status: publish
title: Apache server-side includes on Debian
wordpress_id: '43'
categories:
- Debian
- Linux
- Networking
---

While working through [beginner's guide to ssi](http://www.javascriptkit.com/howto/ssi.shtml), I just could _not_ get it working on Debian by following their instructions. I'm running Apache 1.3, and the AddType mojo just did nothing.

I finally found [this page](http://www.aboutdebian.com/internet.htm), which had the magic. You need another Apache module called mod_includes, so run the following as root:

    
    
    apache-modconf apache enable mod_include 
    
    
    
    You should see this message:
    
    
    
    Replacing config file /etc/apache/modules.conf with new version
    


Restart Apache, and voila. Damn, that took longer than it should have!
