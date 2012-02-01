---
date: '2007-06-06 20:30:36'
layout: post
slug: eeenteresting
status: publish
title: Eeenteresting
wordpress_id: '343'
categories:
- Geek stuff
- Networking
- News
- Spam/UCE
---



![](http://www.phfactor.net/wp-pics/linksysrv042.jpg)


From [the new firewall](http://www.phfactor.net/wp/2007/05/31/vpn-between-osx-and-linksys-rv042048/)'s syslog:


    
    
    Wed Jun  6 17:26:05 2007
    RGFW-IN: BLOCK-SYNFLOOD (TCP 76.171.170.53:34556->204.128.136.1:80 on ixp1) [200,0]
    Wed Jun  6 17:19:22 2007
    SYSLOG_NK-(System Log)Mail sending to [redacted] successfully !
    



Seems like the box think's there's a [SYN flood](http://en.wikipedia.org/wiki/SYN_flood) attack, which is a particular type of [denial of service.](http://en.wikipedia.org/wiki/Denial-of-service_attack)

False alarm? Occurring all along and just now visible? Can't tell. Does make me wonder if my old OpenBSD pf rules were also working on these. pf is amazing for firewalls.

(The IP points to a host on the Road Runner cable modem network, I assume its a [pwned](http://en.wikipedia.org/wiki/Pwned) Windows box.
