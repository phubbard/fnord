---
date: '2008-05-12 15:17:03'
layout: post
comments: true
slug: a-new-wave-of-botnet-attacks
status: publish
title: A new wave of botnet attacks
wordpress_id: '681'
categories:
- Debian
- Geek stuff
- Networking
- Reviews and recommendations
- Spam/UCE
---

This morning, in my inbox, this is what I saw:

[![](http://fnord.phfactor.net/wp-content/uploads/2008/05/denyhosts.jpg)](http://fnord.phfactor.net/wp-content/uploads/2008/05/denyhosts.jpg)That is, 37 reports that a host had tried to break in to my SSH port, and failed more than one password attempt. If I weren't running [DenyHosts](http://denyhosts.sourceforge.net/), the dictionary attacks would have a lot greater chance of succeeding. As it is, I've seen at least 50 hosts blocked today; usually I get one every few days. Sadly, I've not got over **sixty five thousand** hosts denied via DenyHosts, which is a sad commentary on how many cracked Windows machines are out there.

Patch and monitor those boxes, people!
