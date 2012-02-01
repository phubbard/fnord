---
date: '2009-01-22 10:07:12'
layout: post
slug: ze-power-of-python
status: publish
title: Ze power of Python
wordpress_id: '883'
categories:
- Code
- Embedded systems
- Geek stuff
---

![](http://fnord.phfactor.net/wp-content/uploads/2009/01/python-logo.gif)One of the languages I've wanted to learn for a while is [Python](http://python.org/). There's a lot of interesting buzz about it, from[ Dr Chuck](http://www.dr-chuck.com/csev-blog/) and the [google app engine](http://www.google.com/url?sa=U&start=1&q=http://code.google.com/appengine/&ei=g7N4Sd28N5K2sAPbzbQY&usg=AFQjCNHCfdZ55h93nn-bz1Z4f8GdShf8Nw) launch, and after skimming a book it looked quite cool. Going back a bit, Miro at Fermilab wrote their cluster control software in Python, and he and I worked together as his code was a client to my server. I also hacked around a bit in [Sage](http://www.sagemath.org/) for the [ABC project](http://www.phfactor.net/abc/).

However, for me at least, to learn a language I _really_ need a project. Otherwise, as with Ruby, the new knowledge doesn't get used and never transitions to permanent memory. When the chance came up recently at work to use Python on [a NASA project](http://code.google.com/p/nasa-dryden-dt/), I was all over it and have been having an obscenely good time so far. It's fast to learn, easy to code, almost fun to refactor, and has made tricky tasks quite simple. I'm a fan!

Today I found an interesting [article in Embedded Systems](http://www.embedded.com/212901261;jsessionid=MHECHZRF1JPUEQSNDLPSKH0CJUNN2JVN?printable=true), about a new platform from [Synapse Wireless](http://www.synapse-wireless.com/) that uses a Python-based virtual machine for low-power mesh networks, on 8-bit chips. Similar to the [Sun 'Spot' platform](http://www.google.com/url?sa=U&start=1&q=http://www.sunspotworld.com/&ei=7rN4SdG8PJqqtQOphsQ9&usg=AFQjCNETVJp0OQPhtWyreDvkuuzJDra-ag), but Python instead of Java. 

[![](http://fnord.phfactor.net/wp-content/uploads/2009/01/bridge-end-boards-450x145.jpg)](http://www.synapse-wireless.com/?mainID=3&subID=2&type=product&prodID=2)Those are some of the hardware for sale, there's also an eval kit:

[![](http://fnord.phfactor.net/wp-content/uploads/2009/01/ek2100-kitpix.jpg)](http://www.synapse-wireless.com/?mainID=3&subID=6&type=product&prodID=6)

At 149 for the eval kit, I'm tempted. I'm a little annoyed that it doesn't include ADC, though. You have to cough up $380 for their '[network eval kit](http://www.synapse-wireless.com/?mainID=3&subID=6&type=product&prodID=6)' or $145 for the '[end device](http://www.synapse-wireless.com/?mainID=3&subID=2&type=product&prodID=2)' to get that. Which is annoying; the entire **idea** of a sensor network is to have, y'know, _sensors_. 

Anyway.

Unlike the MSP430 ZigBee boards I've messed with, this one has some real advantages:



	
  * Coded in Python! VM only takes 40KB of memory, which is impressive for an 8-bit platform.

	
  * Write and deploy code interactively from the desktop via wireless - sorta like Spot but easier to use.

	
  * Nice terminal strips for connecting your own hardware.




I'm quite tempted, as I've a project in mind that would benefit from the wireless aspect. I really like the idea of Python as portable code for mesh networks; the complexity of coding these things is greatly reduced that way. Brilliant.
