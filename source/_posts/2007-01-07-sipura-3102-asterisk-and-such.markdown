---
date: '2007-01-07 21:10:45'
layout: post
slug: sipura-3102-asterisk-and-such
status: publish
title: Sipura 3102, Asterisk and such
wordpress_id: '276'
categories:
- Reviews and recommendations
- Voice over IP
---

The old (Hitachi WirelessIP 5000):
![WiFi VoIP phone](http://www.phfactor.net/wp-pics/hitachi-5000.jpg)

The new (Sipura/Linksys 3102):
![Sipura/Linksys 3102 interface](http://www.phfactor.net/wp-pics/sipura-medium.jpg)
I had [a fair bit of grief with my Hitachi phone](http://www.phfactor.net/wp/2006/01/06/hitachi-wifi-voip-up-and-running/) and finally eBay'd it off. In its place is the Sipura 3102, a 3-interface device of _considerable_ sophistication. It has FXS, FXO, WAN and LAN ports, meaning that it is:

 



	
  1. A router and firewall

	
  2. An analog phone interface (FXO)

	
  3. A telephone network (PSTN/POTS) interface (FXS)

	
  4. An ethernet bridge

	
  5. A SIP client/server


There are several things I really appreciate about it:

	
  1. Small, low power, **no fans or moving parts**

	
  2. If power fails or VoIP drops, it has a relay to reconnect the analog phone to the wall. Failsafe!

	
  3. Plays well with Asterisk, the VoIP server software of choice.


You connect your existing analog phone to the Sipura, wire it into your network, and voila! Our existing (cordless) phone works a **lot** better than the Hitachi, so this is an enormous win. Once in place, it all seems easy - VoIP in and out, analog in and out, software phones, quite cool...

The outgoing connection is via the commercial service [Broadvoice](http://www.broadvoice.com/), which for 25/month has more-or-less unlimited to most countries we care about. Seems to work pretty well, and we'll **really** be giving it a workout now.


### Getting it working


...took some doing. [This page on InfoWorld](http://weblog.infoworld.com/venezia/archives/2006_12.html) was by far the most useful, and once I fixed my dialplan I was good to go. The [VoIP wiki page](http://www.voip-info.org/wiki/index.php?page=Linksys-Cisco+3102) is also somewhat useful.

Big note: The VoIP **has** to go via the WAN port; the LAN port **will not work.** The Infoworld doc covers this, but I'll also note that you can just configure the Sipura to 'bridge mode' from the Web interface, and don't have to use the PSTN dialing hack.

I also setup QoS (quality of service) on my router, so hopefully other traffic won't screw up the voice connections. I also plugged the Sipura (and analog phone base station) into the UPS, so we'll still have phone if the power goes out.

So far, so good: Recommended!

**Update 10/11/07**: We're now using [Telasip](http://www.telasip.com/) with better results than Broadvoice. Been six months or so now.

**Update 4/16/08**: We had a persistent problem with too-quiet audio; [this page](http://www.jonwsmith.com/projects/asterisk/index.php) explains that gain setting are buried on the 'Regional/Advanced/Miscellaneous' page. Yeesh.

 
