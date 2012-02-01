---
date: '2009-12-08 07:17:00'
layout: post
slug: new-ssh-attack-is-out-there
status: publish
title: New ssh attack is out there
wordpress_id: '1180'
categories:
- Debian
- Geek stuff
- Networking
- Spam/UCE
---

I woke this morning to a slew (here defined as '62') of ssh dictionary attacks:
[![Screen shot 2009-12-08 at 6.40.40 AM](http://fnord.phfactor.net/wp-content/uploads/2009/12/Screen-shot-2009-12-08-at-6.40.40-AM-450x219.png)](http://fnord.phfactor.net/wp-content/uploads/2009/12/Screen-shot-2009-12-08-at-6.40.40-AM.png)

There were already 20 or so last night. Looks like a new botnet/attack wave or similar. I'm using [DenyHosts](http://denyhosts.sourceforge.net/) and quite frankly, **y****ou should be too**.

If you're running Debian, there's [a nice package for it](http://denyhosts.sourceforge.net/faq.html#1_15) that I use and recommend. I've set mine to trigger on 3 attempts, but I've few users and most use ssh keys and not keyboard auth.

Might be a good time to run [chkrootkit](http://www.chkrootkit.org/) and change some passwords!
