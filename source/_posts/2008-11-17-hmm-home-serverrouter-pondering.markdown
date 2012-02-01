---
date: '2008-11-17 08:17:19'
layout: post
slug: hmm-home-serverrouter-pondering
status: publish
title: Hmm. Home server/router pondering
wordpress_id: '841'
categories:
- Debian
- Networking
- Spam/UCE
---

Right now the home network is pretty simple. I've consolidated all of the server functions (web, dns, email, blogs, database, VoIP, etc) into a single Debian box, behind the [Linksys RV042](http://www.phfactor.net/wp/2007/06/06/eeenteresting/) router/firewall. Wireless is provided by a couple of Apple Airport Express boxes (one for G, one for N) and there's also [a gigabit switch](http://www.phfactor.net/wp/2005/06/13/gigabit-ethernet-what-you-need/) as a backbone. Other than the Debian box, the rest are fanless and silent, which has been[ a continuing goal](http://fnord.phfactor.net/2007/01/07/antec-sonata-ii-case-a-brief-review/) once we moved to a much smaller house!

(There's other gear on the net, but it's not relevant here.)

The Debian box has 4 drives in it right now, 1 for Linux and 3 250s in a[ RAID5 hardware array](http://fnord.phfactor.net/2006/11/11/hardware-and-software-raid5-under-linux/):

![](http://www.phfactor.net/wp-pics/sonata2-2.jpg)

This works, and is stable and quiet-er. Or ish. It's _definitely_ not silent, though it's hard to measure noise in any useful way. (I have a decibel meter, and I tried, sorry. Too many variables.)

One idea I've been kicking around is this: Other than disk, everything served by Debian now could run on **much** smaller machine, perhaps even (gasp!) one without fans.

Check this out: It's an [Asus EEE Box](http://www.amazon.com/ASUS-Intel-Processor-Drive-Black/dp/B001DMA0L8/ref=pd_bbs_sr_1?ie=UTF8&s=electronics&qid=1226890862&sr=8-1), a Atom-based PC for under $300:

[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/eee-box.jpg)](http://fnord.phfactor.net/wp-content/uploads/2008/11/eee-box.jpg)

(Wikipedia page is [here](http://en.wikipedia.org/wiki/ASUS_Eee_Box) for more info)

I was just reading [a bit about IPv6](http://arstechnica.com/articles/paedia/IPv6.ars/) and researching what it'd take to add it to the home network, when I found smallnetbuilder.com. It seems to be a really good site for material like this, as well as NAS, wireless and router reviews. S/he likes the [Untangle software bundle](http://www.smallnetbuilder.com/content/view/30539/51/1/1/), which is a polished firewall/filter/router system. I personally prefer OpenBSD for firewalls, as pf can still do the most tricks, but I gotta admit that the GUI polish of Untangle is compelling. Here's a screenshot from [the Untangle site](http://www.untangle.com/):

[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/protocolcontrol_maingui-450x330.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/protocolcontrol_maingui.png)

The files currently on the Debian RAID have mostly migrated to the iMac now (iTunes is quite nice for music management), so losing the RAID array is do-able. I've also got a co-worker with a hand-me-down NAS RAID that might work. So perhaps Untangle or something Debian-based on the Eee Box might work. 

From what I can find, the Linksys RV042 I'm using now lacks IPv6, so something like this is compelling.

Amazing times that we live in, eh? 
