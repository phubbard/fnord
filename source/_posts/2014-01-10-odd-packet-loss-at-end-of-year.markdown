---
layout: post
title: "Odd packet loss at end of year"
date: 2014-01-10 14:44
comments: true
categories: network timewarner motorola pfsense debugging
---

I was debugging a slow network and found a couple of odd problems that I thought worth sharing. Check this out - RRDTool graph from my pfSense firewall, showing latency and packet loss between the firewall and the Motorola SB6141 modem:

![Packet loss graph](https://www.phfactor.net/wp-pics/2014/01/10/before.png)

This is a pecular graph, designed to show link quality. The upper half is latency, in milliseconds, and the lower portion is packet loss, in percent. *Note that packet loss goes from zero to 50% more or less overnight.*

Whut?

Next, notice that it happened right around Jan 1, 2014. At a guess, there's date-related bug in the Motorola SB6141; a power cycle completely fixed the problem:

![No more packet loss](https://www.phfactor.net/wp-pics/2014/01/10/after.png)

That sorted, the network remained slow. I found [this awesome Curl feature](http://askubuntu.com/a/147385) to debug things, and DNS was taking 5-6 seconds per lookup. A dive into /var/log/daemon.log produced lots of DNS errors of this form:

	Error (network unreachable) resolving 'pdns5.ultradns.info/AAAA/IN'
	
Which I found [on this post](http://sgros.blogspot.com/2012/06/bind-and-network-unreachable-messages.html). All you have to do is disable IPv6 support in Bind9; the underlying problem is that DNS is trying to resolve IPv6 addresses when the link doesn't support them. (I'm IPv6-capable here but have it disabled for now.)

So adding "-4" in the /etc/default/bind9 file under options fixed that. 

And it was *still* slow, now because data took 6 seconds to return:

![before fix](https://www.phfactor.net/wp-pics/2014/01/10/curl1.png)

 A pfSense reboot fixed that:
  
![after fix](https://www.phfactor.net/wp-pics/2014/01/10/curl2.png)

I'm assuming it's a bug in pfSense, perhaps a memory leak or something related to the firewall rules. Very odd. There was minimal CPU and memory in use, hard to diagnose.

One last useful trick: I learned [here](http://www.linuxquestions.org/questions/linux-server-73/basic-private-dns-question-928868/) that you can regenerate the root DNS file with a single command:
	dig +bufsize=1200 +norec NS . @a.root-servers.net > named.root
	
Good tools to share. That curl bit for diagnosing HTTP is frickin' awesome.