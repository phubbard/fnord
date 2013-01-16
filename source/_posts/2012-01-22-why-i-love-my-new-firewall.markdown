---
date: '2012-01-22 15:57:16'
layout: post
comments: true
slug: why-i-love-my-new-firewall
status: publish
title: Why I love my new firewall
wordpress_id: '1535'
categories:
- Hardware
- Networking
- Reviews and recommendations
---

As a late Christmas present, I got my [long-awaited](http://fnord.phfactor.net/2008/11/17/why-cant-i-find-this-firewall/) [Netgate 2D3 firewall](http://store.netgate.com/Netgate-m1n1wall-2D3-2D13-Red-P218C83.aspx):  

![firewall](http://fnord.phfactor.net/wp-content/uploads/2012/01/m1n1wall-2D13-red-system.jpg)




My previous firewall was the Cisco/Linksys RV042, a entry-level business unit that worked quite well for years here.




![Unnamed](http://fnord.phfactor.net/wp-content/uploads/2012/01/unnamed.jpg)




There were a few things I wanted that the RV042 couldn't do:




* Better handling of bit torrent. Nothing better for ISOs! The RV042 choked under, I think, large numbers of open TCP connections. Hard to tell if the limitation was CPU or memory or what, which leads to…
* Better instrumentation, visibility and metrics. I want to be able to see how it's performing and if I'm up against limits
* Better filtering and traffic handling.
* Stretch goal: Block all inbound mail connections from any machine running MS Windows. Invariable botnet spam, and one of the niftier tricks possible with OpenBSD and pf.
* Turn-key-grade. I've less time to DIY these days, so I needed something good to go out of the box.


Running [pfsense](http://www.pfsense.org/) 2.0, the new firewall is superb beyond my expectations. The web-based GUI is fantastic, the 500Mhz CPU and 256MB of memory handle more traffic quite ably, and the sheer _depth_ of functionality present is almost daunting. This wee beastie is astounding. Here are some bits I've liked so far:




* RRD graphs for CPU, memory, TCP state tables, rules traffic, etc, etc. Updated via AJAX, no less.
* Nice dashboard showing status and traffic at a glance.
* It ships with nanoBSD installed twice, two partitions on the 4GB compact flash card. The idea is that, if you hose the firewall, you can boot into the second partition and be back up quickly. Haven't tried that, but I love the no-moving-parts flash storage.
* The 2D3 version gives me an extra ethernet port, for later expansion.
* I got the HiFn crypto accelerator, which can do 35MB/sec of AES128.
* Good support for Apple - OpenVPN for laptops, and IPsec for iDevices.
* Nice list subscriptions, so I've subscribed to [IP-based blacklists](http://doc.pfsense.org/index.php/IP_Blocklist) for compromised hosts, ad servers, spammers and the link.
* Transparent HTTP filtering with squid and squid guard. I could also use this for caching if I wanted, but for now it's an easy way to block domains like 2o7.net and the like.


So here are some RRD graphs for a monster bit torrent test, around 200-400 peers.  

Traffic:  

![Screen Shot 2012 01 22 at 3 12 35 PM](http://fnord.phfactor.net/wp-content/uploads/2012/01/Screen-Shot-2012-01-22-at-3.12.35-PM.png)




TCP states, peaking around 3,000:  

![Screen Shot 2012 01 22 at 3 11 54 PM](http://fnord.phfactor.net/wp-content/uploads/2012/01/Screen-Shot-2012-01-22-at-3.11.54-PM.png)




Traffic: Red is upload, set to a 2.0 sharing ratio:  

![Screen Shot 2012 01 22 at 3 11 20 PM](http://fnord.phfactor.net/wp-content/uploads/2012/01/Screen-Shot-2012-01-22-at-3.11.20-PM.png)




The important one, CPU usage:  

![Screen Shot 2012 01 22 at 3 11 35 PM](http://fnord.phfactor.net/wp-content/uploads/2012/01/Screen-Shot-2012-01-22-at-3.11.35-PM.png)




So, roughly speaking, the 20Mbit peak took about half the CPU with the current minimal rules and fire walling. That's not astounding, but I suspect and hope that I can tune it better. Next up, I'm going to try the packet shaping to see what effect that has. Right now, ICMP goes to hell:  

![Screen Shot 2012 01 22 at 3 13 03 PM](http://fnord.phfactor.net/wp-content/uploads/2012/01/Screen-Shot-2012-01-22-at-3.13.03-PM.png)




I've done a simple test with the OpenVPN, which works though I had to buy the Viscosity app to make it work. ($5). Need to get iOS working and see how well that works, that'll be nice to have for the trip to PyCon in March. 




Here's a shot of the web interface:  

![Screen Shot 2012 01 22 at 3 14 59 PM](http://fnord.phfactor.net/wp-content/uploads/2012/01/Screen-Shot-2012-01-22-at-3.14.59-PM.png)




(Yep, I named it 'fratboy.' My old firewall was 'nail.' The theme is 'things that get hammered.' I still think it's funny.)




Other things to look forward to:




* Full IPv6 support (Hi, BenC!)
* Operating-system-based filtering
* Adding a 2-line LCD screen, I want a traffic barograph, and the 2D3 has a serial port I can use.


Overall? For $300 it's a bit steep, but frankly I now regret having bought two RV042s; shoulda gone here years ago. It out-features commercial routers up to two or three thousand bucks, and does so with silence and ~4 watts of power. Yay!




Strongly recommended.



