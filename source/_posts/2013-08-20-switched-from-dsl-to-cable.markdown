---
layout: post
title: "Switched from DSL to cable"
date: 2013-08-20 10:17
comments: true
categories: networking pfsense firewalls dsl cable
---

I've been delighted with my current firewall, a [Netgate m1n1wall 2d13](http://store.netgate.com/Netgate-m1n1wall-2D3-2D13-Red-P218C83.aspx) running [pfSense](http://www.pfsense.org/?option=com_content&task=view&id=40&Itemid=43). I'm happy to recommend both the hardware and software. It even comes in red:

![firewall hardware](https://www.phfactor.net/fnord-images/2013/08/m1n1wall-2D13-red-system.jpg)

I've been using it for a year or so I think, on my AT&T U-Verse DSL connection. It's been reliable and fast, able to handle the 24/3 (mbit) connection even with lots of devices and activity.

Then yesterday, I took advantage of a local promtion. Time Warner Cable is running a one-year discount on connectivity, so I can get about twice the speed for the same price. Specifically, $80/month for 50/5, plus $20 for VOIP.

So the living room stack is now cleaner, smaller and faster:

![cabinet stack](https://www.phfactor.net/fnord-images/2013/08/cabinet.jpg)

(Ignore the audio mixer in the middle, that's another post)

I should note that I went with [the Wirecutter's recommendation](http://thewirecutter.com/reviews/the-best-cable-modem-is-the-motorola-sb6141/) on cable modems and bought the Motorola Surfboard SB6141 via their affiliate link. Seems perfect, though I'm mildly annoyed we need a second box for VOIP, should've seen that coming.

I used a Debian ISO BitTorrent to test it out, as [speedtest](http://speedtest.net) was giving me obviously-bogus 20-ish megabit numbers. A Debian torrent will beat the shit out of pretty much any Internet connection:

![transfer graph](https://www.phfactor.net/fnord-images/2013/08/fast.png)

Looks like TWC provisioned us with almost *sixty megabits* of downlink. Damn.

Low ping too. Frickin' awesome ping, in fact. I should get back into [FPS](http://en.wikipedia.org/wiki/First-person_shooter) games just so I can be a [LPB](http://www.urbandictionary.com/define.php?term=lpb&defid=36431) again:

![pinging google](https://www.phfactor.net/fnord-images/2013/08/ping.png)


As I did the BitTorrent, I kept an eye on the firewall as well. I was using 108 peers, at 58Mbits, but the firewall got seriously laggy. Looking at pfTop, it appears that just handling the interrupts took 70% of the CPU, so the box was running flat-out. This graph underestimates it a bit, but since I forgot to grab a screenshot it'll do for now. That spike Monday is the BitTorrent, and note the lighter color shows time spent handling interrupts. We were slammed.

![cpu graph](https://www.phfactor.net/fnord-images/2013/08/cpu.png)

Looking at [the pfSense docs](http://www.pfsense.org/index.php@option=com_content&task=view&id=52&Itemid=49.html):

	If you require less than 10 Mbps of throughput, you can get by with the minimum requirements. 
	For higher throughput requirements we recommend following these guidelines, 
	based on our extensive testing and deployment experience. These guidelines offer a bit of 
	breathing room because you never want to run your hardware to its full capacity. 
	10-20 Mbps - No less than 266 MHz CPU
	21-50 Mbps - No less than 500 MHz CPU
	51-200 Mbps - No less than 1.0 GHz CPU
	
And my m1n1wall? 500Mhz AMD Geode LX800. Specified as max throughput of 85Mbits, and that's probably with an optimized, zero-rule configuration.

Right, **I need more firewall MIPS to handle this connection.**

## Current options for More pfSense Love
So what are my options? I want pfSense, gotta be fanless with no moving parts so it's silent in operation. Low power a major consideration too. Need a GHz-class processor. Gigabit ethernet preferred, but not required. 

The [Netgate FW-525B](http://store.netgate.com/Netgate-FW-525B-P1919C83.aspx) looks good. Atom 1.8 GHz CPU, 2GB of memory, four gigabit ports, $400:

![Netgate FW-525B](https://www.phfactor.net/fnord-images/2013/08/FW-525B.jpg)

I'm a bit cautious about Atom chips though, having just [upgraded from them on the server](https://fnord.phfactor.net/2013/04/12/server-migrated/), so let's see what else Netgate has available. How about the [FW-754](http://store.netgate.com/Netgate-FW-7541-P1846C83.aspx)? Dual core Atom now, still 1.8GHz but six gig-ethernet ports. Nice form factor, too. $583, ouch.


![Netgate FW-7541](https://www.phfactor.net/fnord-images/2013/08/FW-7541.png)

Oddly, both ship with 60 watt power supplies, which is much higher than I'd like. The server is 22W *max*, and it seems stupid to use more on the firewall. Also, the [525 page](http://store.netgate.com/Netgate-FW-525B-P1919C83.aspx) page says

	Regular operation on this fanless system is fairly high in temperature.

which sucks. Neither is a clear winner, so if you've an idea please leave a comment / email / Tweet. I can live with the m1n1wall for now, but I'm definitely looking to upgrade.

Anyone need a well-treated m1n1wall?

## Notes for others
* TimeWarner cable is, at least here, faster than advertised. You should notice faster web page serving, since the uplink went from 3 to 5 megabits.
* So far, I have a fixed IP with all ports unblocked. No problems with serving HTTP, HTTPS, SMTP and SSH.
* I use [Dyn](http://dyn.com) for DNS, and last week I reduced the TTL on my DNS records to 60 seconds so that when I switched it'd take right away. **Highly recommended** you do the same - services were back within a minute of the connection coming up. If TWC starts changing my IP, pfSense has hooks to update Dyn as it happens; very sweet.
* The Motorola modem seems good. Not paying rent for a TWC modem is a big win.
* pfSense remains the best firewall in my opinion.
* Gawd but I'd love to get Verizon FIOS or Google Fiber here in San Diego!

Most importantly, **firewalls require a fast hardware platform.** That generic Linksys or vendor-provided box is very likely a reason why your connection is slower than it could be. I recommend the m1n1wall for most connections up to 40Mbit, and certainly pfSense is a wonderful system for home or business use.
