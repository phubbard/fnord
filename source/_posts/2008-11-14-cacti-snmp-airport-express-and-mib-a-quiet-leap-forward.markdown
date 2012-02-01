---
date: '2008-11-14 10:37:58'
layout: post
slug: cacti-snmp-airport-express-and-mib-a-quiet-leap-forward
status: publish
title: 'Cacti, SNMP, Airport Express and MIB: A quiet leap forward'
wordpress_id: '833'
categories:
- Debian
- Networking
- Reviews and recommendations
---

It used to be that, if you had corporate funding, you'd buy 'enterprise grade' routers and switches that sported a remote management protocol called [SNMP](http://www.cacti.net/), for Simple Network Management Protocol. Typically, you'd buy a copy of HP's [OpenView](http://en.wikipedia.org/wiki/OpenView) (at around 50,000$) and use it to monitor all of your SNMP devices. Since SNMP actually asks the routers what they're doing, it's precise and has very little network impact. Sorted, as the Brits would say.

Those of us who network as a hobby/home/hacker were left out of this particular nerdvana, and turned to indirect solutions like [Smokeping](http://oss.oetiker.ch/smokeping/), and/or free software like [syslog](http://en.wikipedia.org/wiki/Syslog). Workable but not as good.

However (you knew this was coming, right?) the world has moved on. Prosumer-grade routers like my [Linksys RV042](http://www.linksys.com/servlet/Satellite?c=L_Product_C2&childpagename=US%2FLayout&pagename=Linksys%2FCommon%2FVisitorWrapper&cid=1115416833192) (at all of $149) and [Airport Express](http://apple.com/airportexpress/) (the N version, $99, more on this later) now have SNMP support built in! So that's half of the puzzle. There have also been significant advances on the software side:

[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-61-450x348.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-61.png)

That's [Cacti](http://www.cacti.net/), a web-based SNMP monitor running on my Debian box. It's one of the nicest pieces of programming I've seen in some time, very polished and amazingly easy to use considering the complexity of what it does. You have access control, easy device configuration, many many graph options, and the ability to monitor non-SNMP devices like, say, system load. I've setup a guest account, password guest, that you can [experiment with here](http://www.phfactor.net/cacti/). The data is real, monitoring my firewall's traffic and part of my wireless as well. The guest account is configured to be read-only, so feel free to poke around and experiment.

Let me back up a bit. First off, you need



	
  1. SNMP-capable hardware. My newer Airport Express (b/g/n, part number MB321LL/A) has full support, but the previous b/g (part number M9470LL/A) does not. My RV042 has SNMP, but the more common WRT54 series doesn't unless you install the [third-party Tomato firmware](http://www.polarcloud.com/tomato). (More Airport info is [here](http://blog.cocoia.com/2007/11/06/graph-your-airport-express-extreme-data-throughput-and-more/) and [here](http://james.murty.org/archives/2004/09/15/airport-mrtg/).)

	
  2. A server to run Cacti.




Assuming you have the newer Airport Express or Extreme, run Airport Utility, and go the Advanced tab:




[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-71-450x448.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-71.png)


 


The 'Community string' is the secret name that guards access to SNMP. If you know it, you can access the device. So keep it a secret. Mine isn't really 'Cacti', so there. It's not a big deal for read-only, but some devices allow you to issue commands via SNMP, which_ is_ a big deal. Version 3 of SNMP fixes this, but for now its security through obscurity. To quote Gandalf, "Keep it secret. Keep it safe."


Next up is the firewall, very similar:


[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-51-450x229.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-51.png)




Same drill here. Enable SNMP, set the community name and system info. I leave the trap field blank, more on this below.







Note that SNMP has what are called "MIBs," which are device dictionaries that tell software like OpenView all about the device-specific features. Oddly, Cacti doesn't use MIBs, so you don't need them here, but the [Apple MIB is here](http://docs.info.apple.com/article.html?artnum=120227), and the [Linksys MIB is here](http://www.linksys.com/servlet/Satellite?c=L_Product_C2&childpagename=US%2FLayout&pagename=Linksys%2FCommon%2FVisitorWrapper&cid=1115416833192) FYI.







Next, we go to Cacti, log in as admin and start adding devices, graphs and machines to monitor. It's very simple, so I'll just refer you to [their install docs](http://www.cacti.net/documentation.php). 







I quite like how you have three different graph views at the upper right - list, preview and tree. Preview is nice for this small network, but as you add more the tree view is a natural. As I said above, feel free to log onto the guest account and experiment.




[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-2-450x349.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-2.png)




I also like the Linux stats:




[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-1-450x333.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-1.png)


 

On the negative side there's a few of Cacti limitations to note:






	
  * Cacti doesn't support SNMP traps, or asychronous alerts. This is a showstopper for a serious monitoring system, as you won't get notified when something dies or fails.

	
  * Since it doesn't have MIB support, using vendor or device-specific features requires writing a data query, which I've not yet tried.

	
  * You can't issue SNMP commands from Cacti.


 


While I was learning all of this, I also took detours into [MRTG](http://oss.oetiker.ch/mrtg/) and snmpd and found this nifty Dashboard widget for OSX called [iEyeNet](http://www.apple.com/downloads/dashboard/networking_security/ieyenet.html):




[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-8.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/picture-8.png)Which requires no server, so if you just want a way to peek now and then iEyeNet is a great solution.


Overall I'm thrilled to finally get to play with SNMP, and having views into the state of my network is marvelous. If you poke around, you'll see that I've also setup entries for monitoring non-SNMP hosts via simple pings, which is also nice but less complete. Overall Cacti and iEyeNet are both useful, free and easy to get running.


My wish list looks like this right now:








	
  1. Alerts on failures or traps

	
  2. Ability to look by traffic type, e.g. "Is bittorrent why I'm so slow?"




Overall, SNMP is highly recommended. I'd say flat out not to buy **any** new network hardware without SNMP built in. It's just too useful. 







Update 11/17/08: Cacti works on the iPhone browser too:




[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/img_0001.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/img_0001.png)




[![](http://fnord.phfactor.net/wp-content/uploads/2008/11/img_0002.png)](http://fnord.phfactor.net/wp-content/uploads/2008/11/img_0002.png)






