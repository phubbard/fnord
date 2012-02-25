---
date: '2008-11-17 15:08:36'
layout: post
comments: true
slug: why-cant-i-find-this-firewall
status: publish
title: Why can't I find this firewall?
wordpress_id: '846'
categories:
- Debian
- Embedded systems
- Networking
- Reviews and recommendations
---

We use Bittorrent to download open-source software and also broadcast TV. (Just programs that are over-the-air free, as I don't want the RIAA/MPAA mafia on my case). Unfortunately, bittorrent traffic really slows throughput on our network, and I can't tell if the router or the DSL modem is to blame. I've tried setting BT as the lowest priority on the router, and also using the speed limiting features of the Transmission client we use. Neither solves the problem.

From googling and reading, it seems that the large number of TCP connections opened is the most likely culprit. However, that's inherent to the BT protocol, so although I can limit the number of connections it's not really a solution. From everything I've read, there simply doesn't exist a SOHO router really built to handle the hundreds or thousands of connections.

After reading quite a bit and thinking about it, here's my wishlist:



	
  1. Wired-only router with 10/100 ports. Gigabit is nice but not useful given my connection speed.

	
  2. Fanless, low power, no moving parts. This rules out using an old desktop machine.

	
  3. VPN endpoint with at least PPTP support.

	
  4. SNMP reporting ability.

	
  5. IPv6 dual-stack or 6to4 support.

	
  6. QoS/priority by protocol




These would be nice:








	
  1. Web GUI for setup and configuration

	
  2. More than one IP and port on the LAN side, so I could setup multiple subnets

	
  3. syslog support

	
  4. Ability to have multiple WAN ports - someday I want to try BGP and similar routing.




[M0n0wall](http://m0n0.ch/wall) is really close, but OpenBSD's pf has a few unique tricks I don't think Monowall can do:








	
  1. Packet filtering [based on TCP fingerprint](http://www.openbsd.org/faq/pf/filter.html). This is invaluable for spam blocking, as a rule that says 'no Windows machines can connect to inbound SMTP' is a nearly-complete block for botnet-generated spam.

	
  2. Simple anti-spoofing, activated with a single line.

	
  3. Packet scrubbing. ([Read all about it](http://www.openbsd.org/faq/pf/scrub.html))




After a lot of reading, my current solution looks like this:




[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/net5501_bc_back_big-450x172.jpg)](http://fnord.phfactor.net/wp-content/uploads/2008/11/net5501_bc_back_big.jpg)




That's a [Soekris 5501](http://www.soekris.com/net5501.htm), which at 433 or 500MHz could actually run most of my server software too - more than a little overkill for this. Then again, for $320 its 2 to 3x the price of a SOHO router like my RV042. Liveable, and it's worth it to get the capacity overhead.







**Update 11/25/0**8: The [m1m1wall firewall from Netgate](http://www.netgate.com/product_info.php?cPath=60_85&products_id=562) looks better - $205 instead of 320, preinstalled with pfsense or m0n0wall. 256 vs 512MB, which is no problem. Best of all, you can get it in red!




[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/miniwall2c3antredrear.png)](http://www.netgate.com/product_info.php?cPath=60_85&products_id=562)




For software:








	
  1. [OpenBSD](http://openbsd.org/) plus pf, install via [OpenSoekris](http://opensoekris.sourceforge.net/). **Update - see below, pfsense may be our winner.**

	
  2. [pfw](http://www.allard.nu/pfw/) for GUI management and setup of firewall rules

	
  3. SNMP from OpenBSD is [looking pretty easy](http://www.packetmischief.ca/openbsd/snmp/), and of course syslog and [IPv6](http://www.sans.org/reading_room/whitepapers/firewalls/807.php) are built in.




I like it. I think I'll ebay off the 2U Cisco router, with its fans and 200+ watt heat, and buy one of these instead.




More reading if you're curious:








	
  1. [Slashdot thread on routers](http://tech.slashdot.org/article.pl?sid=08/07/12/2322213), bittorrent, TCP connection limits.

	
  2. [Blog post OpenBSD on Soekris](http://slagwerks.com/blog/index.php/2008/10/10/openbsd-firewall-on-soekris-4501/)

	
  3. [SmallNetBuilder on Untangle](http://www.smallnetbuilder.com/content/view/30539/51/), which is similar but Linux-based

	
  4. [OpenBSD on Soekris plus state-preserving failover](http://michiel.vanbaak.info/soekrisobsdcarp.htm) (CARP, more advanced than I can use here.)

	
  5. [Soekris product page](http://www.soekris.com/net5501.htm).

	
  6. Soekris also sells [a HiFn-based VPN accelerator chip](http://www.soekris.com/vpn1401.htm), which can be added later if I need it. Nice.

	
  7. [IPv6 intro](http://arstechnica.com/articles/paedia/IPv6.ars/) and [IPv6 wiki](http://wiki.go6.net/index.php?title=Main_Page).


As an amusing footnote, I was [researching gigabit switches with SNMP support](http://www.askbjoernhansen.com/2005/02/11/gigabit_switch.html), so that I could monitor my backbone using Cacti. You can now get **24 ports** of SNMP-managed gigabit for $300 [from Netgear (GS724T)](http://www.netgear.com/Products/Switches/SmartSwitches/GS724T.aspx), but the amusing part is that the 16-port version costs the same! Ahh, someday when I outgrow my 8-port maybe.

**Update 11/18/08**: Commenter timf points me to [pfsense](http://www.pfsense.org), which I had missed, and appears to meet every one of my wishes. Oops. OK, less work for me. Thanks!

**Update 11/25:** Added m1m1wall hw/sw combo.









