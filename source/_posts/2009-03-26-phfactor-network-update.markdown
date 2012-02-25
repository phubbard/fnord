---
date: '2009-03-26 14:44:56'
layout: post
comments: true
slug: phfactor-network-update
status: publish
title: phfactor network update
wordpress_id: '936'
categories:
- Geek stuff
- Networking
- News
---

OK, had to call AT&T, but TCP port 25 is now unblocked, as per [this thread](http://www.broadbandreports.com/forum/r21673251-ATT-Uverse-and-Outgoing-Mail-and-FreeBSD), and so inbound email is working again. I have to figure out outbound via SSL/TLS and such, but at least mail should be getting delivered here OK.

The tech put the modem/router in our living room, which is cool but problematic: The server, usul, that runs phfactor is noisy, and poorly suited to the room.

[![img_0114](http://fnord.phfactor.net/wp-content/uploads/2009/03/img_0114-450x600.jpg)](http://fnord.phfactor.net/wp-content/uploads/2009/03/img_0114.jpg)

Today I managed, over the course of a couple hours, to setup WDS using two Airport Expresses, with the net result (pun intended) that usul now lives upstairs, and its ethernet goes to an airport express. That connects to the one in the living room, and the result is that of a 'virtual ethernet cable' between the two. Sounds simple but took a while and several factory resets to get working. We'll see how reliable it is; I also had to lose the faster speeds of 11n since one of the Airports was B/G only.

I'm a bit nervous, in that I've never entrusted my only server to a wireless-only link before, but running cat5 here is basically impossible. Fingers crossed. If this dies I might have to go HomePNA or something.
