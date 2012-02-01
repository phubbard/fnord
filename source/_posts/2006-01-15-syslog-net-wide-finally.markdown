---
date: '2006-01-15 16:02:56'
layout: post
slug: syslog-net-wide-finally
status: publish
title: Syslog net-wide, finally
wordpress_id: '42'
categories:
- Debian
- Networking
- Reviews and recommendations
---

I'm debugging some network problems, Apache issues and the like, and finally [setup a syslog server](http://www.aboutdebian.com/syslog.htm) for the home network.

Turns out that even the [airport express](http://www.apple.com/airportexpress/) has syslog support in it. Nice, that. 

So now I'm syslogging from Linksys and Apple, and as a bonus I got rid of those incredibly annoying 


    
    
       Jan 15 12:12:41 usul -- MARK --
    



messages in the log. Choice.

The key bit is to edit /etc/init.d/sysklogd where it says

    
    
    SYSLOGD=""
    


and change it to

    
    
    SYSLOGD="-r -m0"
    



I realize that I am, in fact, incredibly lame for taking this long to implement it. Ahh well. Highly recommended.

**Update 6/6/07**
Somewhere in there Debian changed again, and now you edit

/etc/default/syslogd

to add the -r -m0 bit. Yeesh. See [this nice article](http://www.aboutdebian.com/syslog.htm) for more details and some nice examples of setting up a central log server for a complex network.
