---
date: '2007-10-17 15:45:20'
layout: post
comments: true
slug: new-features-in-osx-105
status: publish
title: New features in OSX 10.5
wordpress_id: '510'
categories:
- Macintosh
---

Browsing [the list of new features](http://www.apple.com/macosx/features/300.html) (300 claimed), a few jump out at me. I preordered my copy already on Amazon, and am really looking forward to this. Been a long time coming.



	
  1. Although its not well known, 10.4 already supports SmartCards via the [MUSCLE framework](http://www.linuxnet.com/). ([Apple page here](http://developer.apple.com/documentation/Security/Conceptual/Security_Overview/Security_Services/chapter_4_section_7.html#//apple_ref/doc/uid/TP30000976-CH204-DontLinkElementID_1)) You can [flip a (hidden) switch](http://docs.info.apple.com/article.html?artnum=304035), and voila! Your login screen sports a government logo. I dug into this a few years ago, but foundered on the smart cards. You easily get cards and readers that Mac recognizes, but the code to _program_ the cards is basically unavailable. Jumping back to the present, 10.5 supports the 'PIV' standard:


> Let your smart card do more. Now you can use a smart card to unlock FileVault volumes and your keychain, and configure your Mac to lock the screen when a smart card is removed. Leopard supports the PIV standard for Federal employees and contractors.


PIV is [Personal Identity Verification, AKA FIPS 201](http://www.smartcardalliance.org/newsletter/october_2005/feature_1005.html). It requires contact (magstripe or similar) as well as RFID functions. Eeeenteresting...wonder if mortals like me can program them? Update: Just found [](http://www.powerdeveloper.org/article.php?article=smartcard)[this page that covers card init](http://www.powerdeveloper.org/article.php?article=smartcard) and programming. Now where did I leave that hardware...

	
  2. A small thing, but you can now embed calculations in the search window, just like google:


![](http://images.apple.com/macosx/features/images/300_spotlight_calculations_20071016.png)




	
  3. Dictionary app now integrates Wikipedia content when online. Handy! I use wikipedia daily, this'll be useful.

	
  4. iCal has gotten much stronger. Group scheduling, availability, booking resources (e.g. conference rooms) and a bunch of other useful additions. Looks like it wants a [CalDAV](http://en.wikipedia.org/wiki/CalDAV) server to do all this magic, dunno yet if there's a free one out there. Update: [there is](http://rscds.sourceforge.net/installation.php). Several, actually. [Even Apple's code is OSS](http://trac.calendarserver.org/projects/calendarserver)!

	
  5. There's something with Mail that allows notes to sync with iPhone, [seemingly via IMAP magic](http://daringfireball.net/linked/2007/october#wed-17-leopard). I _still_ want real sync, because otherwise the iPhone notes are a dead-end. Waiting and seeing on this one.

	
  6. Everyone now [geotagging your JPGs](http://www.flickr.com/groups/geotagging/), Preview is now up on your game:


> Get real information from your photos. If your image has embedded GPS metadata, Preview will show you exactly where that perfect photo was taken. Open the Image inspector and select GPS. Preview pinpoints the location where you took the photo on a world map. From there you can even open the GPS location in Google Maps.


Kewl.

	
  7. Terminal gets tabs. I've [switched to iTerm](http://www.phfactor.net/wp/2007/03/16/iterm-and-distraction-free-computing/), but I'll have to try Terminal again.

	
  8. RSS integrated into email. Interesting idea.

	
  9. TextEdit opens and edits MS Word 2007 documents. Useful, that!

	
  10. [TimeMachine](http://www.apple.com/macosx/leopard/features/timemachine.html) looks awesome. Time to buy more disks. They say it works over [AFP](http://en.wikipedia.org/wiki/Apple_Filing_Protocol), so maybe I can just backup to my [Debian box running netatalk](http://viebrock.ca/article/22/file-sharing-from-linux-to-os-x-a-quick-guide).

	
  11. Kernel much improved - POSIX 1003.1, SUSv3, DTrace, better threading, 64-bit apps.

	
  12. Ruby on Rails now shipped in the box! Xcode v3! Ruby support for Rendezvous/Bonjour.


There's a lot more on [the list](http://www.apple.com/macosx/features/300.html), but those are the ones that jumped out at me. This looks good!
