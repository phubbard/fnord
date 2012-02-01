---
date: '2007-09-18 16:10:08'
layout: post
slug: do-you-know-what-time-it-is
status: publish
title: Do you KNOW what time it is?
wordpress_id: '473'
categories:
- Geek stuff
- Reviews and recommendations
- Watches and timekeeping
---

Or do you just _think_ you know?

Me, I **know**. Check this out:


![](http://www.phfactor.net/wp-pics/p1000929-wpa.jpg)




![](http://www.phfactor.net/wp-pics/p1000932-wpa.jpg)




![](http://www.phfactor.net/wp-pics/p1000931-wpa.jpg)


That, my friends, is a [Tempus LX CDMA](http://www.endruntechnologies.com/network-time-server.htm) stratum-one network time server. A network time server addresses a problem [near and dear to my heart](http://www.phfactor.net/wp/?cat=11), namely keeping a set of computers time-synchronized. Like many interesting problems, it's much harder than it sounds. This toys costs just under five thousand dollars, and it's cheap compared to some others.

The backstory is amusing, too. A few years ago, I wrote [a whitepaper on network time synchronization](http://it.nees.org/library/telepresence/network-time-synchronization.php), which was geared towards the problem of distributed data streaming. Some time earlier this year, Tempus (vendor) found it via Google and offered a **free** server if they were added to the whitepaper!

By that time, I had switched groups, but my colleagues agreed and voila! Hardware, with attendant donation paperwork. Can I bring home the bacon or what? This is the first time [my NEESit tech writing](http://it.nees.org/library/search.php?IncludeBlogs=3&Template=doculiba&search=Paul%20Hubbard&searchdoculib=%3E%3E) has been so directly praised, and I'm as proud as can be.

Of course, we don't really need one of these. UCSD and SDSC have their own NTP servers, as does any large network. So right now its sitting in my office, and when I have time I'll rack it with [the Sun](http://www.phfactor.net/wp/2007/02/21/good-toys/) just for grins. What a cool toy!

For you time nerds out there, and wavelets folk - unlike most others, this one doesn't look for GPS signals. It uses the CDMA cellular network (e.g. Verizon) which requires very accurate clock sync to do handoff and spreading functions. So, without even a cellular account, it can sync deep inside buildings with just the included cheap 5/7ths whip antenna. Damned clever, that. I'm impressed, and I'd say that even if they hadn't bought and paid for my integrity. ;)
