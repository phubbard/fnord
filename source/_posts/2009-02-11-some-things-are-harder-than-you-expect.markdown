---
date: '2009-02-11 17:07:27'
layout: post
comments: true
slug: some-things-are-harder-than-you-expect
status: publish
title: Some things are harder than you expect
wordpress_id: '893'
categories:
- Debian
- iPhone
- Macintosh
---

Inspired by the recent news that Google now has [free sync of calendars and address books](http://www.google.com/support/mobile/bin/answer.py?answer=139195), I set off to try and get the following working:



	
  1. I want to share a group called 'shared' from my address book to Chris and her iPod touch. (There's a bunch of other entries she doesn't want.)

	
  2. We really need a family calendar that we can both easily view and edit, for stuff like daycare outages, pediatrician visits, house guests and the like. If at all possible, push sync to iPhone/iPod would rock.




(Experienced geeks will by now be rolling on the floor and having trouble breathing.)







Things that didn't work well enough:








	
  1. The Google '[Calaboration](http://code.google.com/p/calaboration/)' tool works with existing Google calendars and events. You can't share your existing data to Google and then sync that, so you have to move events into the Google calendars manually. Ug.

	
  2. The addressbook sync to Google, accessed via iTunes, works well buuuut:

	
    * It syncs _everything_ - I had to manually clean up the entries from my little-used gmail, delete dups, etc.

	
    * Google now has your full addressbook - it's all or nothing. I'm not [paranoid](http://ascii.textfiles.com/archives/1717), but I dislike this.




	
  3. Next, following [these instructions](http://www.macworld.com/article/132736/2008/04/caldavserver.html), and [this must-read](http://www.macworld.com/article/132876/2008/04/workingmac2505.html) also, I installed[ Darwin Calendar Server](http://trac.calendarserver.org/) (DCS) on our iMac. Basic setup is OK, but if you want much there's no docs and precious little help on the net. I'd like to have separate calendars for each of us, plus a shared calendar for Anna stuff, and even that is quite difficult. (I'm [not alone in this](http://www.afp548.com/article.php?story=20080221204044797), it seems.)

	
  4. After a while with that, I head-slapped myself when I discovered that[ Debian now has a 'calendarserver' package](http://newsgroups.derkeiler.com/Archive/Uk/uk.comp.sys.mac/2008-11/msg00560.html) with DCS neatly rolled up! I prefer to run servers on the Debian anyway, so this is excellent. Edit two files in /etc/caldavd and... well, not voila, because you're back to the problems of step #3.

	
  5. I've now got my calendar and the shared calendar working, and one for Chris, but I can't figure out how to subscribe to her calendar and vice-versa. The idea would be to start with 'I can see but not edit her calendar' and progress to delegated write access. I have a group setup with both of us as members; maybe all my calendars need to be inside the group?? The [docs are studiously vague](http://trac.calendarserver.org/wiki/XMLDirectoryService).




It looks like shelling out a jaw-dropping $500 for OSX Server would solve a lot of this, but we don't really _have_ that much spare cash. It looks like, once you get DCS working, you can use [BusySync](http://www.busymac.com/) or [NuevaSync](http://www.nuevasync.com/) to do the wireless-push; I'll post on that if I get that far.




Needless to say, my goals and expectations are being scaled back quite rapidly. Other avenue to explore:








	
  1. [Zimbra](http://www.zimbra.com/) works and is recommended by [Stacey](http://robotmonkeypants.com/), but is almost as costly as OSX to get shared addressbook support.

	
  2. [OpenLDAP](http://www.openldap.org/) seems to work as an addressbook server, and there are [apps to push an existing book](http://www.addressbookserver.com/projects/abxldap/index.jsp) into it.

	
  3. Google Apps [does contact sharing](http://www.google.com/support/a/bin/answer.py?answer=60218) as well.

	
  4. There's also this [nice page of general alternatives](http://www.macworld.com/article/138481/2009/01/mobilemealternatives.html).


Overall, I highly recommend pursuing this if you want to feel like an idiot. It's working for me.



