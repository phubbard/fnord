---
date: '2008-02-29 10:34:43'
layout: post
comments: true
slug: might-be-time-to-upgrade-the-wireless
status: publish
title: Might be time to upgrade the wireless
wordpress_id: '606'
categories:
- Geek stuff
- Macintosh
- Networking
- Reviews and recommendations
---




![](http://www.phfactor.net/wp-pics/tn9479_tc_front.jpg)


Via [TidBits](http://db.tidbits.com/article/9479), news that the new [Apple Time Capsule](http://www.apple.com/timecapsule/) is shipping. Its a combination device with a WiFi router and internal hard drive. The WiFi is the new 2.4/5GHz [802.11n](http://en.wikipedia.org/wiki/802.11n), which increases both the speed and the range of the network. According to [the Wikipedia page](http://en.wikipedia.org/wiki/802.11n), going from 802.11g (which most computers made in the past 3-4 years have), you go from 38m to 70m in range and 19 to 74 megabits of usable throughput.

I'll pause so that the nerds reading this can cease drooling. That's a big jump in range and speed, which naturally leads to the question of 'What do I _do_ with that much bandwidth? I mean, my internet connection is much slower than that.'

In a word: Backups. OSX 10.5 introduced [TimeMachine](http://www.apple.com/macosx/features/timemachine.html), integrated backup software of _stunning_ polish and elegance. I've spent years with software of varying capability, so trust me when I say that stunning is not an exaggeration. cpio, tar, rsync, unison, windows backup (shudder), ufsdump, Retrospect... it's a long list. I still use cron and rsync for Debian on this server, but it's got serious limitations and my main defense is to replace the hard drive every two years. TimeMachine solves all these, in an automatic fashion that's tied into the operating system itself.

Let me explain. If you use a third-party backup program, consider what happens when the drive fails. You have to reinstall the operating system itself, usually a manner of hours, _then_ install the backup/restore program, _then_ restore the backups. With OSX, you boot the install DVD and select the 'Restore from TimeMachine backup' option. Vive la difference, baby.

So, motivation established, you consider 802.11n routers. However, if you're like me you have older machines that don't have 802.11n and can't afford to upgrade them all. You're then faced with the hassle of running **two** wireless networks, one slow and one fast. Double the fun it ain't.

Time Capsule (seemingly) solves a lot of these. And some others. Right now, I use an older [Airport Express](http://www.apple.com/airportexpress/) (802.11g) plus[ a LaCie NAS drive](http://www.lacie.com/products/product.htm?pid=10882). It mostly works, but since the LaCie is RAID0 I'm actually more at risk; if either drive in the NAS fails I lose all my backups. And it's slow as well, even over gigabit. In contrast, the Time Capsule uses a single drive, which is server-grade:


> Chulani clarified that the "server-grade" drives in a Time Capsule are the same 7200 rpm drives used for Apple's Xserve servers, and that they have a higher mean time between failure (MTBF) rating than consumer drives. The MTBF for server-grade drives is often 1 million hours (114 years), which is a measure of probability; in this case, that out of a set of drives with similar properties, an extremely high percentage will still be fully functional after several years.


(That's from [the TidBits article](http://db.tidbits.com/article/9479))

The phrase from TidBits that got me really interested was this:


> AirPort Utility 5.3 also adds setup features that enable you to migrate settings from an existing base station into the Time Capsule; to set up a dual-band network, with an older base station operating at 2.4 GHz and the Time Capsule set to 5 GHz; and to set up a roaming network with multiple base stations connected over Ethernet.


If I'm reading that correctly, it sounds like the TC can run somehow with another WiFi router? Hmm. I don't have Airport Util 5.3 and can't find a download URL, so this is hard to verify.

The TimeCapsule costs $299 for 500GB and $499 for 1TB, which is quite good. If I can get it to replace or complement my Airport Express, it'd be fabulous.

Update: [Nice review and walk-through](http://gizmodo.com/362391/time-capsule-initial-verdict-smooth-sailing-no-surprises) on Gizmodo.
