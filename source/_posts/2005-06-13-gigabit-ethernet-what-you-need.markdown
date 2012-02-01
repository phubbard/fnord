---
date: '2005-06-13 14:12:27'
layout: post
slug: gigabit-ethernet-what-you-need
status: publish
title: Gigabit ethernet - what you need
wordpress_id: '4'
categories:
- Networking
- Reviews and recommendations
---

For several years, those of us with home networks have been running 10/100 mixed LANs, usually with switches here and there. Works well, cheap, reliable and easy to wire. Very few indeed have home gigabit; the adapters are cheap but switches have been very expensive.However, that's no longer the case.


## Goals


Cheap, reliable, low-power, no cooling fans. Oh yeah, I want fast, too, so we need jumbo frames (9000 byte packets instead of 1500; makes a huge difference in performance) and a fully non-blocking switch.

This is all on twisted pair, indoors, for home use.

For my network, I need an 8 port switch; you may be able to get by with less.


## Cut to the chase!


If you need 8 ports, the best option I've found is the [SMC 8508T (Amazon, non-affiliate link)](http://www.amazon.com/exec/obidos/tg/detail/-/B0000AKA95/qid=1108072034/sr=8-1/ref=sr_8_xs_ap_i1_xgl23/102-3980408-2513710?v=glance&s=electronics&n=507846). $100, jumbo frames, 15W power, no cooling fans, 16Gbit bisection bandwidth, decent blinky lights:


![Product image](http://www.phfactor.net/smc8508t.jpg)


If you can live with fewer ports, the otherwise-identical 5-port version is the [SMC 8505T (Amazon again)](http://www.amazon.com/exec/obidos/ASIN/B0000AKA94/qid%3D1108072400/sr%3D11-1/ref%3Dsr%5F11%5F1/102-3980408-2513710) for $67:


![Product image](http://www.phfactor.net/smc8505t.jpg)


About the only disadvantage of either one is that they use a wall-wart power supply instead of an internal. On the plus side, the do come with both rubber feet and rack ears. These are both really nice little switches in my opinion.


## Which network card should I buy?


For network cards, I like the [3Com 996BT (ZipZoomFly)](http://www.zipzoomfly.com/jsp/ProductDetail.jsp?ProductCode=250045), about $60 from various venders. The [Intel Pro 1000/XT](http://www.zipzoomfly.com/jsp/ProductDetail.jsp?ProductCode=251402) (130, ZZF) is also supposed good and reasonably cheap. If you've got the cash, the best card is the [SysKonnect SK9821 (Froogle, appx $100)](http://froogle.google.com/froogle?q=syskonnect+9821&btnG=Search+Froogle). To get good throughput, PCI-X or 66/64 is pretty much required. Otherwise, you'll get 2-3X faster than fast Ethernet at best.

Given that the SysKonnect prices have fallen fast (they used to cost $500) I'd recommend the 9821. I ended up with 3C996's, since I bought them a while ago when SysKonnext cost 6X more. Note that the 996 is actually a Broadcom chip, and uses the Tigon 3 driver (tg3) in Linux.

Many motherboards now have gigabit included on them as well. Bonus, that.


## Read For Yourself


This page represents quite a bit of research for me, and I've just presented my conclusions. However, you don't have to take my word for it!

Anthony Betz and Paul Gray at Iowa did an [excellent review of gigabit/copper cards](http://www.cs.uni.edu/%7Egray/gig-over-copper/gig-over-copper.html) that is where my recommendations come from. Read and be enlightened.



	
  * Anthony Betz and Paul Gray at Iowa did an [excellent review of gigabit/copper cards](http://www.cs.uni.edu/%7Egray/gig-over-copper/gig-over-copper.html) that is where my recommendations come from. Read and be enlightened.

	
  * For more about jumbo frames, read [this commercial page](http://www.small-tree.com/jumbo1.htm) and [this WAN-based page](http://sd.wareonearth.com/%7Ephil/jumbo.html). I'm not sure I buy the huge improvements they graph, but you'll get the idea.

	
  * If you want to know if a piece of hardware supports jumbo frames, dig into the tech specs. If it doesn't say jumbo frames are supported, assume they are not! This [page at Oregon has a nice list of hardware](http://darkwing.uoregon.edu/%7Ejoe/jumbo-clean-gear.html) with and without jumbo support.




## Things To Watch Out For





	
  * It's pretty much impossible to tell online if a switch has cooling fans or not. Since most of them use the 40mm size, they make lots of noise and fail quickly. Google, or check it out in person. I've gotten a lot pickier about noise of late, so this was a showstopper for me.

	
  * Not all jumbo frames are created equal. Vendors have been know to call 82 extra bytes a jumbo. You want 9000 or better.

	
  * My Dell Optiplex GX280's came with an onboard Gig-E card, a Broadcom BCM95751. It uses the same driver as my 3C996, but can't do jumbo frames! I have the same machine under XP, and no jumbo there either. Hardware limitation.

	
  * Despite having gigabit on their laptops years before anyone else, Apple Powerbooks do not support jumbo frames.

	
  * No, this will not speed up your DSL connection.

	
  * If the first speed test you try is scp/sftp, you'll be disappointed. However, PSC has a 7-line patch to scp that speeds it _way_ up. Like 10X faster. [Go and get it.](http://www.psc.edu/networking/projects/hpn-ssh/)




## So why bother?





	
  * High geek value.

	
  * It is faster, after all.

	
  * You can beat down anyone who complains about lag at your next LAN party.


Most importantly: The hardware is now down around the cost levels of slower 10/100 gear, so there's no reason to pay 10 bucks less on a switch when you can get gigabit.

Go for it.

Update 10/3/07: See [this updated post](http://www.phfactor.net/wp/2007/10/04/more-cool-networking-gear/) for a revised switch/router too.
