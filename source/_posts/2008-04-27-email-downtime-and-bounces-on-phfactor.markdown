---
date: '2008-04-27 20:53:07'
layout: post
slug: email-downtime-and-bounces-on-phfactor
status: publish
title: Email downtime and bounces on phfactor
wordpress_id: '672'
categories:
- Debian
- Geek stuff
- Networking
- News
---

**Non-geek summary:** Email was down to phfactor for a few days due to a local problem. It's back now, and I have tools to keep an eye on things.

**Geeky details**: I run exim4 on Debian, and had tweaked the config for dual-port (25/587) for SMTP inbound and outbound. One of the recent Debian updates borked something, such that

    
     -oX 25:587 -oP /var/run/exim4/exim.pid


was no longer valid, and thus exim refused to run. Oops. As a workaround, I've removed the port settings (meaning I have to use a different SMTP server when out and about, so this'll get fixed later as time permits) and it's back to running.

Having been bitten numerous times by similar problems, where one of many Debian updates will break a service, I spent some hours today researching server monitoring software beyond the Smokeping I have running already. I wanted something that could query a running service over TCP/IP and see if all was good. I came up with [Monit](http://www.tildeslash.com/monit/index.php) via [this post](http://www.ubuntugeek.com/monitoring-ubuntu-services-using-monit.html), and have it up and running now. Here's a screenshot:

[![](http://fnord.phfactor.net/wp-content/uploads/2008/04/monit-ss-450x528.jpg)](http://fnord.phfactor.net/wp-content/uploads/2008/04/monit-ss.jpg)
(click for full size)
Seems pretty good, decent list of native protocols that it understands. Right now it's passworded off, not sure if I'll remove the login or not. Seems mostly harmless to publish, since most of the monitored stuff is only accessible from this side of the router.

**Update**: Password will remain, as the webpage allows you to stop/start services! What a vulnerability **that** is, yeesh.
