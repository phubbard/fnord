---
date: '2010-03-18 09:25:19'
layout: post
comments: true
slug: site-outages-routing-failing
status: publish
title: Site outages - routing failing
wordpress_id: '1230'
categories:
- Networking
- News
---

My trusty Linksys/Cisco RV042 has decided to crap out. Monit has been sending alerts for the past few days, but tracking it down was proving difficult since it mostly happened during the day. Yesterday I was home in the afternoon to [sign for a package](http://twitter.com/phubbard/status/10576504406) and managed to catch the failure in person.

First hint - server and access point lose ethernet link:

[![Screen shot 2010-03-17 at 3.31.24 PM](http://fnord.phfactor.net/wp-content/uploads/2010/03/Screen-shot-2010-03-17-at-3.31.24-PM-450x333.png)](http://fnord.phfactor.net/wp-content/uploads/2010/03/Screen-shot-2010-03-17-at-3.31.24-PM.png)

That should _never_ happen. Ever. Indicates hardware failure...

Wander over and the router is just showing the yellow failure LED:

[![routerfail](http://fnord.phfactor.net/wp-content/uploads/2010/03/routerfail-450x468.jpg)](http://fnord.phfactor.net/wp-content/uploads/2010/03/routerfail.jpg)

I [did some research](http://www.smallnetbuilder.com/content/view/30237/51/) and the RV042 is still the best model for what I want: months of uptime, good firewalling, PPTP VPN, 55Mbit WAN->LAN, done. I really considered the RVL200, but in the end it was too late to cancel the Amazon order. ;)

Anyway, replacement arrives tomorrow, please bear with us until then, as we'll have continuing intermittent outages.

PS The failing unit is on a UPS, and has an Ethernet surge suppressor on it, though it _could_ be the power supply itself. Very odd.

**Update 3/20/10**: Router replaced last night. Should be smooth running from here out! Replacement was quite easy due to the ability of the RV042 to save and load a settings file via the browser. The only glitch was the U-verse modem must have the router in its 'DMZ Plus' mode, and that's keyed to MAC address, so I had to cable into the u-verse and configure that. Ten minutes start to finish.
